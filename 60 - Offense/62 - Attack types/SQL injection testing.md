`I am not too familiar with SQL, so to learn [[SQL injection|SQL injection]], I would like to mess around with my own database. This database is called `sakila` and it is premade.

The main table, `customer`, has a list of customers and their information:
![[Pasted image 20221116213544.png]]
There are 599 customers total, each with an id, store id, first name, last name, email, address id, creation date, and modification date.

# Basic queries
### SELECT
Let's start with some normal queries. We can find people based on their name:
`SELECT * FROM customer WHERE first_name="JOHN";`
which returns John Farnsworth, customer ID 300.

We can also find customers that have a certain range of IDs:
`SELECT * FROM customer WHERE customer_id>100;`
which returns the 499 customers with an ID above 100.

We can combine queries as well:
`SELECT * FROM customer WHERE customer_id>100 AND address_id<110;`
which returns the 5 customers with an ID above 100 and an address ID below 110.

We can grab specific columns:
`SELECT first_name, last_name, email FROM customer WHERE active=0;`
which returns the first name, last name, and email of customers with inactive accounts.

### ORDER BY
To sort a table that is being returned, you have to choose a column:
`SELECT * FROM customer ORDER BY first_name;`
which returns all the customers sorted alphabetically by first name.

You can also choose a column by its number:
`SELECT * FROM customer ORDER BY 3;`
which returns the same as `first_name` because that is the third column.

# UNION queries
There is also a table called `staff` that lists the staff of each store. There are different columns in the `staff` table and the `customer` table, so if we want to grab both at once, we have to grab specific columns.

For example, we can grab the names of all the staff and the customers:
`SELECT first_name, last_name FROM staff UNION SELECTION first_name, last_name FROM customer;`
which works because the column data types match: both are strings.