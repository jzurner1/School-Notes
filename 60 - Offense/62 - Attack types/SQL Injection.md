SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its SQL database. It may allow an attacker to view information that they normally wouldn't be able to such as login information.

There are a few variations, such as UNION attacks.

# Basic examples
### Retrieving hidden data
[Example lab](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data)
For example, a website may use the following URL:
`https://target.com/products?category=Gifts`
This URL might make the following SQL query:
`SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
This asks the database to return all products that are in the gifts category and have been released.

An attacker might be able to enter the following URL:
`https://target.com/products?category=Gifts'--`
which, in turn, sends the following SQL query:
`SELECT * FROM products WHERE category = 'GIFTS'--' AND released = 1`
The `--` characters indicate that the rest of the line is a comment, so the database will ignore that part of the query and show all gifts, regardless of if they've been released. Note that some SQL servers use different comment syntax.

To go further, an attacker might be able to enter the following URL:
`https://target.com/products?category=Gifts'+OR+1=1--`
which would send the following query:
`SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1`
The modified query will retrieve all results where the category is gifts or where 1 equals 1. Because `1=1` is always true, all items will be returned.

### Subverting application logic
[Example lab](https://portswigger.net/web-security/sql-injection/lab-login-bypass)
Imagine a website that allows users to log in with a username and password. If a user enters the username "Steve" and the password "P4ssw0rd", the SQL query might look like this:
`SELECT * FROM users WHERE username = 'Steve' AND password = 'P4ssw0rd'`
If a user is matched, it logs them in. Otherwise, they are rejected. Imagine, however, that an attacker enters "administrator'--" as their username and skips the password:
`SELECT * FROM users WHERE username = 'administrator'--' AND password = ''`
If the admin account's username is administrator, they will be logged in.

# How to find SQL injection vulnerabilities
Most SQL injections can be found using automated tools, such as Burp Suite's web vulnerability scanner. There are a few ways this can be done:
- Submitting the `'` character and looking for errors or other anomalies
- Submitting some SQL-specific syntax that evaluates to the original value (such as `AND 1=1`) and syntax that evaluates to a different value (such as `AND 1=2`) and looking for differences in the responses
- Submitting payloads designed to trigger time delays when executed with an SQL query, and looking for differences in response time