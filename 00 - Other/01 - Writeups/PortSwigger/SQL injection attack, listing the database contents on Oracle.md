# Description
This lab contains an SQL injection vulnerability in the product category filter. The results from the query are returned in the application's response so you can use a UNION attack to retrieve data from other tables.

The application has a login function, and the database contains a table that holds usernames and passwords. You need to determine the name of this table and the columns it contains, then retrieve the contents of the table to obtain the username and password of all users.

To solve the lab, log in as the `administrator` user.

# Process
I assumed that this lab was similar to the one for non-Oracle databases, so I started off by trying some things in the URL. After a few queries that returned errors, I sent `category='+UNION+SELECT+NULL,NULL+FROM+dual--`. It took me a minute to remember that Oracle has a dual database and I can't just select NULL from nothing.

I knew that I couldn't try querying `information_schema.tables` like in other databases, so I did some [quick research](https://chartio.com/resources/tutorials/how-to-list-all-tables-in-oracle/) and found that you can query from `user_tables`. The request I made was `category='+UNION+SELECT+table_name,NULL+FROM+user_tables--`, which returned the table name of `USERS_UERLXK`.

To find the names of the columns, I did some more research and came across [this article](https://dataedo.com/kb/query/oracle/list-columns-names-in-specific-table). Using that, I made the query `category='+UNION+SELECT+column_name,NULL+FROM+sys.all_tab_columns--`. I may have been able to do it from `user_tables` like in the last query, but this worked.

There were hundreds of columns returned, so I searched through them. I found the column names `USERNAME_TZZXYD` and `PASSWORD_KZLNPK`, which looked right. I sent in `category='+UNION+SELECT+USERNAME_TZZXYD,PASSWORD_KZLNPK+FROM+USERS_UERLXK--`, and that gave me the administrator login!