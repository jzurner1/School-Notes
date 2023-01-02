# Description
This lab contains a blind SQL injection vulnerability. The application uses a tracking cookie for analytics, and performs an SQL query containing the value of the submitted cookie.

The results of the SQL query are not returned, and no error messages are displayed. But the application includes a "Welcome back" message in the page if the query returns any rows.

The database contains a different table called `users`, with columns called `username` and `password`. You need to exploit the blind SQL injection vulnerability to find out the password of the `administrator` user.

To solve the lab, log in as the `administrator` user.

# Process
This lab took place in a store with products, where each product had its own product page. On the top of the page was a "Welcome back" banner, indicating that I was logged in to some account. Each request included a `TrackingId` that was presumably the target of this lab, based on the exercises I had completed.

The first step was to see if there was a difference between using the TrackingId and not using it. When sending a normal request with the ID, the "Welcome back" banner showed up; when sending a request without the ID, the banner was not shown.

To start out, I sent `TrackingId=kvzsq8BONiaFylFJ' AND '1'='1;`, which returned the "Welcome back" banner. This indicated that the page was vulnerable, but just to make sure, I sent `TrackingId=kvzsq8BONiaFylFJ' AND '1'='2;`, which didn't show the banner.

My first step in determining the password was using the payload from the exercises:
`xyz' AND SUBSTRING((SELECT password FROM users WHERE username ='Admin'), 1, 1) > 'm`
This didn't work, so I tried again with `< 'm`. This also didn't work, and neither did `== 'm`, so I was confused. I guess that would be too easy.

From now on, I need to specify that a getting a content length of 11010 means that the query is true and 10949 means the query is false.