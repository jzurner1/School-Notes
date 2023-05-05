A blind SQL injection is when an application is vulnerable to [[SQL injection|SQL injection]] but errors and the results of queries are not shown in HTTP responses. This makes attacks such as UNION attacks ineffective because they rely on seeing the results.

Consider an application that uses tracking cookies. Requests will include a cookie header like this:
`Cookie: TrackingId=u5YD3PapBcR4lN3e7Tj4`
When these requests are processed, the application will determine whether this is a known user with a SQL query:
`SELECT TrackingId FROM TrackedUsers WHERE TrackingId='u5YD3PapBcR4lN3e7Tj4'`
This specific query is vulnerable to SQL injection, but the results will not be returned to the user.

# Conditional responses
One method for exploiting SQL injection is by triggering conditional responses.

In the example above, the website will know if a user has been there before and can print "Welcome back" if the TrackingId matches one that is stored. To test for SQL injection, you could append conditional values to the cookies:
`Cookie: TrackingId='u5YD3PapBcR4lN3e7Tj4' AND '1'='1`
`Cookie: TrackingId='u5YD3PapBcR4lN3e7Tj4' AND '1'='2`
If the injection is successful, the first result will return the "Welcome back" message because the conditions are both true. The second result will not return the message because its second condition isn't true.

This can be used for determining any specific part of the database. For example, the following query tests for the first letter of the admin's password:
`xyz' AND SUBSTRING((SELECT password FROM users WHERE username ='Admin'), 1, 1,) > 'm`
In essence, it takes the admin's password (inner parentheses), takes the first letter of it (outer parentheses), and compares it to the letter M. If it is greater (later in the alphabet) than the letter M, it returns true and thus shows the "Welcome back" message. This can be repeated for each letter.

Potential conditional response:
- `xyz' AND SUBSTRING((SELECT password FROM users WHERE username ='Admin'), 1, 1,) > 'm` - Test the value of the first character of the password string and compare it to a chosen character. Evaluates to true if the character matches the requirements.