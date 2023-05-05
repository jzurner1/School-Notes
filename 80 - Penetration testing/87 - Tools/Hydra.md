

# Websites
Hydra works for brute-forcing passwords on websites, but it works best if you already know a username or password.

Hydra has some requirements for password cracking:
- Username or wordlist for usernames
- Password or wordlist for passwords
- IP address or hostname
- HTTP method (POST/GET)
- Directory/path to the login page
- Request body for username/password
- A way to identify failed attempts

The basic syntax is `hydra -L <username list> -P <password list> <target IP/hostname> <protocol>`.

For example, I want to break a password on the website `target.com`. I currently don't know either the username or the password, but the website tells me whether or not a username exists in the first place. I will be using a username list (stored at `/home/kali/Documents/resources/wordlists/usernames.txt`) and a random password. I know the hostname is `target.com`

The HTTP method can be found by opening the Network section of inspect element and entering a login. You can see what method is used to send that login. You can also use Burp to intercept a request.

The path to the login page is just `/login`, and the request body can be found by opening Burp and seeing what the request body is. That can be copied directly.

A way to identify failed attempts is usually just text on the page. You can copy the text directly; in this case, the text is `Invalid username`.