# Description
This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs an SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and no error messages are displayed. But the application includes a "Welcome back" message in the page if the query returns any rows.

The database contains a different table called `users`, with columns called `username` and `password`. You need to exploit the blind SQL injection vulnerability to find out the password of the `administrator` user.

To solve the lab, log in as the `administrator` user.

# Process
This lab took place in a store with products, where each product had its own product page. On the top of the page was a "Welcome back" banner, indicating that I was logged in to some account. Each request included a `TrackingId` that was presumably the target of this lab, based on the exercises I had completed.

The first step was to see if there was a difference between using the TrackingId and not using it. When sending a normal request with the ID, the "Welcome back" banner showed up; when sending a request without the ID, the banner was not shown.

To start out, I simply added an apostrophe to the end of the `TrackingId`. Originally, the content length was 4991, but after attaching the apostrophe, it was 4930. This reduction was presumably the disappearance of the "Welcome back" banner.

Next, I tested to see if it was actually SQL injection. I submitted the `TrackingId` with `'+AND+'1'='1`, which would evaluate to be true. This returned a length of 4991, indicating that SQL injection was possible. I also tried `'+AND+'1'='2;` and received 4930, which gave me a baseline for successful (4991) and an error or invalid (4930).

### Table information
I wanted to figure out what database type was being used, so I used the process of elimination. First, I tried `'+AND+1=1--`. This didn't give an error, so I knew it wasn't MySQL (which requires a space before the comment). Next, I tried `'+UNION+SELECT+NULL--;`, which also didn't give an error. I knew that this meant that it wasn't Oracle, as Oracle requires a table to be used (such as `SELECT NULL from DUAL`). To try Microsoft, I did `'+AND+'a'||'b'='ab'--;`, which didn't fail either. This indicated that the database was PostgreSQL, as Microsoft uses `'a'+'b'` to combine strings.

To test for table names and content, I did `'+UNION+SELECT+password+FROM+users--;`, which didn't give an error. This told me that there was a table called `users` with a column called `password`. Assuming there was a `username` column, I tried `'+UNION+SELECT+username+FROM+users--;`. This also worked, so I had the two important column names and the table name.

### The administrator's password
Finally, I had to figure out how to extract the administrator's password. First, I tried `'+AND+SUBSTR((SELECT+password+FROM+users+WHERE+username='administrator'),1,1)>='a'--;`, which didn't give me an error. This told me that there was a user named `administrator`, presumably the admin account.

To actually find the password, I had to go through letter-by-letter. I did it manually for the first letter, running through `'+AND+SUBSTR((SELECT+password+FROM+users+WHERE+username='administrator'),1,1)>'m'--;` until I had pinned down the first letter. For each letter after, I used Burp Intruder with `=` instead of `>`, and ran through each letter in each slot until I found the right one. This was tedious but it worked; I soon had the final password. I logged in and completed the lab.