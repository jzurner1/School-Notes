# Description
This lab has an admin panel at `/admin`, which identifies administrators using a forgeable cookie. Solve the lab by accessing the admin panel and using it to delete the user `carlos`. You can log in to your own account using the following credentials: `wiener:peter`

# Process
The description for this lab gave away most of the information. First, I went to the login page and logged in with the provided credentials. Next, I opened Burp Suite and navigated to the `/admin` page, and intercepted the request.

The request included a cookie called `Admin` with the value `false`. I changed this to `true` and forwarded it to receive access to the admin control panel. From there, I deleted the Carlos user (I had to intercept that request and change the cookie as well) and completed the lab.