# Description
This lab contains an SQL injection vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.

To solve the lab, display the database version string.

# Process
This lab seems to be the exact same as [[SQL injection attack, querying the database type and version on Oracle|the other one]], just with MySQL and Microsoft instead of Oracle. For that reason, I'll be skipping ahead so I don't have to repeat what I already know.

First, I tried to find how many columns there were:
`category=gifts'+UNION+SELECT+NULL,NULL%23`
I used `#` as the comment symbol here, so I had to encode it. This didn't return an error, so I learned there were two columns.

I looked up how to find the version string, and I found that the query was usually just `SELECT VERSION()`. I plugged that in as `category=gifts'+UNION+SELECT+VERSION(),NULL%23`, and that gave me the version string when I reloaded the page. The lab was solved.