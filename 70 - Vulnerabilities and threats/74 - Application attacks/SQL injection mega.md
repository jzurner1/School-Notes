# Basics
SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its SQL database. It may allow an attacker to view information that they normally wouldn't be able to such as login information.

### Example 1
Imagine a website uses the URL `https://target.com/products?category=Gifts`. For this URL, the website will take the value of `category` (in this case `Gifts`) and plug it into an SQL query, probably something like `SELECT * FROM products WHERE category = 'Gifts' AND released = 1;`.

This query will return all of the items in the `products` database that match the description, in this case items that have been released and exist in the gifts category.

Now, assume that an attacker wants to see all the products, including those that haven't been released. First, they will want to test if SQL injection even exists here. To do that, they could type the URL `https://target.com/products?category=Gifts'`, which would create the query `SELECT * FROM products WHERE category = 'Gifts'' AND released = 1;`

Notice that there are two apostrophes after the `Gifts` keyword. This is a syntax error, and will thus not work. The website may display an error or do something that isn't expected.

Now, the attacker knows that the website is vulnerable to SQL injection. As a basic query, they could do something like `https://target.com/products?Gifts'--`, which would create the query `SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1;`

While this may look similar, the two dashes are a comment symbol (for some types of database). That means that everything after them will be ignored, so the query will essentially be `SELECT * FROM products WHERE category = 'Gifts'`, which will show all products, even if they haven't been released.