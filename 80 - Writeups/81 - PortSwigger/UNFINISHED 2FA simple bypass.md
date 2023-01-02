# Description
This lab's two-factor authentication can be bypassed. You have already obtained a valid username and password, but do not have access to the user's 2FA verification code. To solve the lab, access Carlos's account page.

-   Your credentials: `wiener:peter`
-   Victim's credentials `carlos:montoya`

# Process
To start, I simply tried to log in to the victim's account. I intercepted the requests with Burp Proxy, but I didn't see anything that could obviously be used to gain access to the account.

There is also an email client that can be used to receive emails for peter's account. Using that, I logged into peter's account to see how it worked. I logged out and went back to trying to log into montoya's account. After messing around with it for a bit, I figured that it wasn't the right solution and moved on.

After doing a bit of reading on the PortSwigger website, I went back and logged in with peter's account. I sent each request to Burp's Repeater to examine later, and possibly just skip a step in the authentication process. Next, I logged out an went back to log in as montoya.

During this step, I looked at the requests. When logging in, it sent a GET request to `/login2` (the MFA step) followed by a GET request to `/my-account` after providing the MFA code. To bypass the MFA, I simply replaced `/login2` with `/my-account`, which allowed me to login without MFA. This solved th