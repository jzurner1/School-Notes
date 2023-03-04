# Description
This lab's password reset functionality is vulnerable. To solve the lab, reset Carlos's password then log in and access his "My account" page.
- Your credentials: `wiener:peter`
- Victim's username: `carlos`

# Process
For this lab, I was given the login for myself and the username of the target. The website is a simple blog, and given the description of the lab, I started out by logging in. From there, I was given an email address.

Next, I logged out and opened Burp Suite. At this point I had a pretty strong assumption about how the solution would go. In the login page, I pressed "forgot password", then it asked for a username or email. I typed in `carlos`, and then intercepted the outgoing request with Burp.

Next, I sent that request to Burp Repeater. Looking at the request and response, I didn't see what I had expected. The body of the outgoing request simply contained `username=carlos`, and the incoming response didn't have anything new. I had initially expected the lab to be as simple as changing the specified email.

My next theory involved starting out by resetting my own password. I typed my username in the "forgot password" box and pressed submit, then opened the email client. I received an email containing a link with a URL that contained a temporary password token, which I assumed was the actual target.

After clicking the link, I entered the new password and intercepted the request. This request actually specified the username being reset. I changed the username to `carlos` and sent it on. Finally, I returned to the account page and logged in with the new password.