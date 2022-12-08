# Description
This lab contains an SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.

The application has a login function, and the database contains a table that holds usernames and passwords. You need to determine the name of this table and the columns it contains, then retrieve the contents of the table to obtain the username and password of all users.

To solve the lab, log in as the `administrator` user.

# Process
## The website
Like some of the other labs, this was a shop with only the item names and descriptions. From this I assumed that the injection would take place in the URL and with the item categories.

Categories that I selected were reflected in the URL and as the page title. Visiting the URL `https://target.com/filter?category=Pets` would put the word Pets on the title. To test for injection, I first put in `category=abc` as the URL. No items were returned, but abc was on the title. Next, I tried using an apostrophe as `category='`. This gave an internal server error.

## UNION queries
Assuming that this was like previous labs, I skipped ahead and tried a UNION query, `category=1'UNION+SELECT+NULL--`, which gave an error. I tried with another NULL, which didn't give an error, so that meant that there were two columns.

I made some guesses as to the names of the table. `users` didn't work, and neither did `logins` or `accounts`. `products` worked, but that wasn't what I needed; at least it showed that my queries were correct. I tried `profiles`, `names`, and `users`, but none worked.
## information_schema.tables
I remembered that in theory, I could get a list of tables by making a query to `information_schema.tables`. I tried `category=1'+UNION+SELECT+NULL,NULL+FROM+information_schema.tables--`, which didn't give an error, meaning that the table existed. After some research, I tried `1'+UNION+SELECT+table_schema,table_name+FROM+information_schema.tables--`, which returned a massive list of tables. This was helpful, but I had to sort through them.

Because I returned the table schema as well as the table names, I could see which tables were actually useful. One of them, `users_zmkfed`, seemed to have what I wanted. I tried `category=1'+UNION+SELECT+username,password+FROM+users_zmkfed--` but received an error.

Next, I tried another information_schema request, this one from .columns. I did `category=1'+UNION+SELECT+column_name,NULL+FROM+information_schema.columns--`, which gave me an even longer list of tables. After searching through it, I found the columns `username_ytxalm` and `password_vacdqg`, which seemed to match the format of the users table name.

All of this culminated in one more query that actually worked - `category=1'+UNION+SELECT+username_ytxalm,password_vacdqg+FROM+users_zmkfed--`. It listed all of the usernames and passwords that I could get. I took the administrator username and password, logged in, and completed the lab.