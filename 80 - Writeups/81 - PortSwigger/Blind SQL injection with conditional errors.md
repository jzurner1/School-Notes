# Description
This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs a SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and the application does not respond any differently based on whether the query returns any rows. If the SQL query causes an error, then the application returns a custom error message.

The database contains a different table called `users`, with columns called `username` and `password`. You need to exploit the blind SQL injection vulnerability to find out the password of the `administrator` user.

To solve the lab, log in as the `administrator` user.

# Process
This lab started out with the same website as the other PortSwigger labs; a simple store with categories and products. Users are tracked with the `TrackingID` cookie, which will presumably be the subject of the lab.

### Getting the idea
To begin, I opened Burp Suite and intercepted a request. This request included a `TrackingId` cookie containing my unique tracking ID. Based on the lab practice, I figured that I would need to use the `CASE` keyword.

For some background, the `CASE` keyword is effectively an if/else system for SQL. It has the format:
```
CASE
	WHEN condition1 THEN result1
	WHEN condition2 THEN result2
	ELSE result3  // optional, if not included, returns NULL for other results
END
```

Or, more simply: `CASE WHEN condition1 THEN result1 ELSE result2 END`, which is what will be used in this lab.

For the condition, we obviously want to test the value of each character of the password, which can be done with `username = 'administrator' AND SUBSTRING(password, 1, 1) = 'a'`.

### Starting out
First, I found a way to compare results. If the condition is an error, the page will return an internal server error; if it isn't, the server will return OK, regardless of if the condition is true. First, I sent a request with a true condition:
`trackingId' AND (1/1=1) AND 'a'='a`
This resulted in a 200 OK response. Next, I tried a false condition:
`trackingId' AND (1/0=1) AND 'a'='a`
This also resulted in a 200 OK response, which I expected. Lastly, I tried a condition with an error:
`trackingId' AND (1/0=1) AND 'a'='a`
This resulted in a 500 internal server error, which I also expected.

Now, I can move on to trying other things. First, I tried to incorporate the `SELECT CASE` utility:
`trackingId' AND (SELECT CASE WHEN (1=2) THEN 1/0 ELSE 'a' END)='a`
Ideally, this would have evaluated the case to be false, and moved to compare `'a'='a'`, which would be true, and return a 200 OK response. Unfortunately, this gave a 500 internal server error, indicating that something was wrong with the syntax.

Next, I tried the Oracle database syntax:
`trackingId' AND (SELECT CASE WHEN (1=2) THEN TO_CHAR(1/0) ELSE 'a' END FROM dual)='a`
This one worked. I received a 200 OK response when the condition was `1=2` and a 500 internal server error when the condition was `1=1`. This was what I was hoping to see.

Before doing anything else, I flipped around the results to make it work more logically:
`trackingId' AND (SELECT CASE WHEN (1=1) THEN 'a' ELSE TO_CHAR(1/0) END FROM dual)='a`
Now, a true condition will result in a 200 OK response code and a false condition will result in a 500 internal server error response.

### Substrings
After cleaning that up, I moved on testing basic substring queries:
```
trackingId' AND (SELECT CASE WHEN (SUBSTR('xyz', 1, 1) = 'x') THEN 'a' ELSE TO_CHAR(1/0) END FROM dual)='a
```
As I had hoped, this worked. Using `x` as the comparison returned a 200 OK response code, while any other letter returned a 500 internal server error.

I could finally move on to testing the database itself. First, I tried the straightforward method:
```
trackingId' AND (SELECT CASE WHEN (username = 'administrator' AND SUBSTR(password, 1, 1) > 'a') THEN 'a' ELSE TO_CHAR(1/0) END FROM users)='a
```
This was based on the fact that I know there is a `users` table, `username` and `password` columns, and a user named `administrator`. Unfortunately, this didn't work, even after replacing `>` with `<` and `=`.

### Solving it
After an hour or two of troubleshooting, I realized that my issue stemmed from the `CASE` keyword. The subquery grabbed the `users` table, but didn't specify which row to use. I had to specify a row:
```
trackingId' AND (SELECT CASE WHEN (username = 'administrator' AND SUBSTR(password, 1, 1) > 'a') THEN 'a' ELSE TO_CHAR(1/0) END FROM users WHERE ROWNUM=1)='a
```
This, finally, returned a 200 OK response code.

As I have done before, I sent that request to Burp Intruder. After running it, I received the admin password, logged in, and solved the lab.

### Alternative solution
After solving the lab, I looked at the intended solution. It turns out that the intended query, with the tracking ID, was:
```
trackingId'||(SELECT CASE WHEN SUBSTR(password,2,1)>'a' THEN TO_CHAR(1/0) ELSE '' END FROM users WHERE username='administrator')||'
```