# Description
This lab is vulnerable to username enumeration and password brute-force attacks. It has an account with a predictable username and password, which can be found in the wordlist.

To solve the lab, enumerate a valid username, brute-force this user's password, then access their account page.

# Process
This was fairly easy. I started by plugging in some random values for the username and password, and intercepting the login request with Burp Suite. I sent it to the Burp Intercepter and used the provided wordlist for the usernames.

After letting it run for a couple minutes, it returned the username `puppet`, so I plugged it into the username field. Next, I used the provided password wordlist and used Burp Interceptor again to find the password of `666666`. I logged in and it completed the lab.