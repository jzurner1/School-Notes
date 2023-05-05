SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its SQL database. It may allow an attacker to view information that they normally wouldn't be able to such as login information.

There are a few variations, such as UNION attacks.

# Characteristics
Most SQL injection attacks tend to use one or more of the following:
- **Unfiltered escape characters**: If an input field includes special characters used by SQL or the scripting language, they might be mistaken for a command.
- **Improper input types**: If an application is too trusting, data inputs could be submitted that are the wrong type. For example, entering a string into a numeric field may cause an error.
- **Stacked queries**: Appending additional forged queries onto the original legitimate one. Without input filtering, a semicolon could end a query and start a new one, which could be anything the attacker wants.
- **Blind injection**: Some servers hide SQL error messages to prevent users from getting access to information. Blind injection statements can create verifiable changes in page output or cause server delay to find information.
- **Signature evasion**: Network intrusion detection systems often monitor for SQL injection, so many attacks are formatted to avoid detection.


A secure web application does the following:
- Sanitizes input by filtering or substituting dangerous characters that could modify SQL queries
- Validates input by making sure all data is in the expected format before submitting a query
- Restricts the privileges of both users and the application to limit the damage that injection can do
- Restricts end-user error information to a minimum to prevent attackers from using error messages to learn about server vulnerabilities


# Examples
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
If a user is matched, it logs them in. Otherwise, they are rejected. Imagine, however, that an attacker enters `administrator'--` as their username and skips the password:
`SELECT * FROM users WHERE username = 'administrator'--' AND password = ''`
If the admin account's username is administrator, they will be logged in.


MySQL uses the pound sign for comments, so it is possible to use this for injection. A normal login may use the following query:
![[Pasted image 20221116220649.png]]
assuming that the user entered `Mike` in the username field and `123abc` in the password field.

If the user enters `Mike";#` as the username, it ends up with this query:
![[Pasted image 20221116220843.png]]
Notice how the part of the query that checks the password is commented out. This will allow an attacker to enter anything for the password and still get access to an account.

# How to find SQL injection vulnerabilities
Most SQL injections can be found using automated tools, such as Burp Suite's web vulnerability scanner. There are a few ways this can be done:
- Submitting the `'` character and looking for errors or other anomalies
- Submitting some SQL-specific syntax that evaluates to the original value (such as `AND 1=1`) and syntax that evaluates to a different value (such as `AND 1=2`) and looking for differences in the responses
- Submitting payloads designed to trigger time delays when executed with an SQL query, and looking for differences in response time