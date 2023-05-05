# Background
Altoro Mutual is a website to practice web attacks. It is an imaginary bank and you are given the login `jsmith` and `Demo1234` to practice with.

# Process
## Logging in as admin
To test if the login page was vulnerable to SQL injection, I first used the login `name` and `password`, which returned a standard "username or password not found" response. Entering an apostrophe returned an error, indicating that the page was vulnerable.

By default, I assumed that the page makes a query like `SELECT * FROM users WHERE username='<input>' AND password='<input>'`. When I added an apostrophe to the query, it did `username='''`, which caused an error.

Next, I tried the payload `'OR 1=1;--`, which should have given me some good results. Unfortunately, the website asked for a password, and after I entered some gibberish, it gave me an error about the semicolon.

I tried again with the username `'OR 1=1--` and another gibberish password. This time, it actually logged me in as an administrator, so that was cool!

At this point I didn't really know what to do, so I stopped. I may continue this later.