Loading up the Juice Shop, I wasn't sure what to expect. I had never used it before but I had heard that it was one of the best applications for messing with.

The basic page is, as you would expect, a juice shop. Each item has a price, details, and reviews, and there is an option to create an account and login. There are 35 items total and a search bar to manuever through the page.

# Admin login
The first thing I wanted to try was SQL injection in the login field. I plugged in a random email and a password that ended with an apostrophe, but nothing happened. I added an apostrophe to the email, which triggered an error. Instead of saying "Invalid email or password", the page said "\[object Object\]". A popup appeared saying that I had solved the challenge called "Error handling" by provoking an error that was not gracefully or consistently handled.

Next, I plugged in `asd' OR 1=1;` as the username, and pressed enter. Apparently this was all I needed to log in as the administrative user; I received another popup saying that I had solved the challenge "Login Admin" by logging in with the administrator's user account.

Next, I went to the admin account and noticed that there were some things in the cart. I figured that ordering that might reveal some vulnerabilities. When given the new option, I added a new address and entered `<img src="test" onerror="alert('hello')">` in every field that I could find. Unfortunately, this didn't seem to do anything.

On the order confirmation page, the URL was `http://localhost:3000/#/order-completion/5267-0411b255bd0009a6`. I was curious to see if that last part could be used for an IDOR (I think that's what it is, I'm not too sure), but it didn't show any immediate results in cyberchef so I moved on.

# Testing SQL injection
Returning to the login SQL injection, I wanted to try some more with it. I found that the minimum query I could enter into the email field and still get access to the admin account was `' OR 1=1;`, which implies that the query was something along the lines of `SELECT * FROM users WHERE username = '' AND password ='';`. The injected query would then be `SELECT * FROM users WHERE username = ''OR 1=1;' AND password ='';`. This could be useful for other things.

One of the biggest issues I ran into was that no matter what query I entered, I would always received either "Invalid email or password" or "\[object Object\]". It seemed like whenever I entered valid syntax, I would get the former, and whenever I had incorrect syntax, I would get the latter.

After a bit more messing around, I found that I could check conditions. I could do this with the query `admin@juice-sh.op' AND <condition>;`; for example, `admin@juice-sh.op' AND 1=1;` would log me in as the administrator while `admin@juice-sh.op' AND 1=2;` would return "Invalid email or password". This was made even easier with the Burp Suite Repeater tool, which allowed me to quickly change conditions and check them without having to log out each time.

Before doing anything else, I figured it would be helpful to learn what database was being used. To do this, I first used string concatenation to test for errors. On Microsoft databases, you can concatenate strings with `'string1'+'string2'`, so I submitted the value `admin' '@juice-sh.op';`. This gave an error. Next, I tried `'string1'||'string2'`, which is used by both Oracle and PostgreSQL databases. Specifically, I used the query `admin'||'@juice-sh.op';`, which logged me in as admin. I had narrowed it down to two databases, but I still had to figure out which of them it was.

Among other differences, PostgreSQL allows the use of both `SUBSTR` and `SUBSTRING` while Oracle only allows `SUBSTR`. When I plugged in the query `admin@juice-sh.op' AND SUBSTRING('ABC123', 1, 3) = 'ABC';`, I was logged in, which indicated that the database was PostgreSQL.

At this point, I noticed that in the responses to my requests, actual errors were being given. For example, if my query was just `admin@juice-sh.op'`, I would get a response stating that there was an unrecognized token. I wanted the challenge, so I decided to ignore this and keep working without the extra information to see if I could do it.

Next, I wanted to find out the password to the administrator's account. I did that with a subquery within the previous `SUBSTRING` query. It ended up being `admin@juice-sh.op' AND SUBSTRING((SELECT password FROM users WHERE email='admin@juice-sh.op'), 1, 1) = '';`, and I sent it to Burp Intruder, plugging in characters to find the proper responses. Most of them gave a 401 status code with a length of 385, but the number 0 gave a 200 status code and a length of 1180. That told me that the password started with a zero.

I continued on with each character to get the password of `0192023a7bbd73250516f069df18b500`, which didn't work on the login page. After a bit of confusion I realized that the "password" I had just gotten was probably the hashed version of the actual password. Fortunately, Crackstation had the actual password stored and recognized the hash for me, giving me the password of `admin123` which, to be honest, I probably could've just brute-forced much more easily. I received another notification that I had solved a challenge by logging in with the actual password.

# API hacking
After looking around a bit, I found that one of the pages when making a purchase makes a GET request to `/api/addresss`. I figured it might be worth checking other API sources to see if any of them were usable. I turned on the Burp Proxy and started recording each page's requests to get a list of APIs that were being accessed.

The APIs that were referenced included `/api/Addresss/7` and `/8`, `/api/BasketItems`, `/api/Cards`, `/api/Cards/3` and `/7`, `/api/Challenges`, `/api/Challenges/?name=Score%20Board`, `/api/complaints`, `/api/complaints/2`, `/api/Deliverys`, `/api/Deliverys/1` and `/2`, `/api/Feedbacks`, `/api/Feedbacks/8`, `/api/Products/24`, `/api/Quantitys`, `/api/SecurityAnswers/`, `/api/SecurityAnswers/20`, `/api/SecurityQuestions`,  and `/api/Users`.

Going in order, I started with `/api/Addresss/7` and `/8`. Both of them returned fake addresses that I had entered for previous orders. I continued on and tried other numbers, but they were all blocked with errors saying that malicious activity was detected. I even ran it through the Burp Intruder with numbers 1 through one thousand, but only those two worked.

`/api/BasketItems` returned a list of my current basket items and `/api/Cards` returned a list of cards that had been used for payments. `/api/Cards` worked in much the same way as `/api/Addresss` in that none of the numbers could be accessed.

`/api/Challenges` gave a list of challenges that could be completed on the Juice Shop website. It included a surprising amount, so there would be a lot to do. `/api/Challenges/?name=Score%20Board` just gave the specific challenge listing for finding the scoreboard.

`/api/complaints` gave a list of the complaints that were were submitted, `/api/Deliverys` gave a list of delivery method options, `/api/Feedbacks` gave a list of submitted website feedback, `/api/Products` gave a list of products, `/api/Quantitys` gave a list of the quantities of products, `/api/SecurityAnswers` gave an error, `/api/SecurityQuestions` gave a list of possible security questions, and `/api/Users` gave a list of users and their email addresses.