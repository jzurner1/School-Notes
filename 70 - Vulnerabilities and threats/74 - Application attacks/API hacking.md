In many web applications, APIs are used to get information from behind the scenes. Occasionally, these APIs are vulnerable to attacks. 

# Generic University
To provide examples, I will be using the [Generic University](https://github.com/InsiderPhD/Generic-University) tool, which provides an intentionally vulnerable webpage.

### What I did
The Generic University GitHub lists a number of goals to complete:
1.  Find the emails of the administrator
2.  Brute force the API to find new endpoints
3.  Find out what grades everyone got in a class
4.  Edit someone's grade
5.  Make an account
6.  Access the GraphQL API
7.  Change another account's password
8.  Login to your account
9.  Access admin API
10.  Find out what vulnerabilities the IT admins have ignored
11.  Make your account an admin
12.  Access the admin control panel
13.  Fire a blind XSS in the admin control panel and validate with your new admin account
14.  Delete everything
15.  Restore everything
I wanted to complete them all, if I could.

After setting up and launching the Generic University website, I went to my localhost IP to check it out. I was taken to a home page that was apparently under construction. At the top of the screen was a logo that I could click to reach the home page as well as a Login button. On the bottom of the page was a Contact IT button and a Report a Security Vulnerability button.

I launched Burp Suite and clicked on the login page. It asked for an email address and a password, for which I had neither. After entering some information and checking the requests and responses, I decided to move on.

Seeing that there was a `/login` page, I tried `/register`, which existed. On that page I entered a name, email address, and password, and it logged me in. This was a good step. After logging in, I returned to the home page. On my way there, I noticed that a request was made through Burp for `/api/users/6`. I sent that request to the Burp Repeater.

The first thing I tried was changing the number. I set it to `/api/users/7` and got back some information for a person named Dr. Kianna Kautzer. Their ID was 7 and the API also returned a role ID, which was 3.

I tried again with the ID 1 and 0. 1 was a student and 0 was not found. Lastly, I sent in the request without an ID (`/api/users`), which returned a list of users and their information. This was great, but I still didn't know what each role ID meant. I could make assumptions; students seemed to have an ID of 2, professors had 3, and IT had 1.

Now, I want to find the email addresses of the administrators to complete the first goal. I could assume which of the users were administrators from the previous test, but I wanted to be sure. To do this, I started brute forcing the API to find new endpoints. Below is a list of the successful endpoints that I tried; I will explain the results after:
- `/api/admin/`: Contains some more endpoints
- `/api/roles/`: Contains a list of role IDs
- `/api/users/1/`: Contains information about user with ID 1; nothing new
- `/api/grades/`: Contains list of grades by each user

The admin endpoint gave a list of two sub-endpoints and their functions: `/restore`, said to restore the database from the last manual backup, and `/delete`, said to delete everything from the database without backing up. These will be useful for later goals, but for now I'll skip them.

The roles endpoint is helpful for identifying the role IDs from earlier. It lists 9 different roles: 1, 4, and 7 are for admins, 2, 5, and 8 are for students, and 3, 6, and 9 are for teachers. Returning to the users endpoint, I can find which users are admins. Their emails are `ynitzsche@grant.com`, `michel.hyatt@yahoo.com`, and `victoria.spencer@hotmail.com`. All other users are teachers or students without admin privileges.

At this point I had completed goals 1 (find administrator emails), 2 (brute force the API to find new endpoints), 3 (find the grades for a class), 5 (make an account), and 8 (login to your account).

My user ID is 22, my user's name is Bob, the email is `bob@email.com`, and the role ID is 2, indicating that I am a student. My next goal is to try and change that role ID with POST requests. I planned to do this to the `/api/users/22` endpoint.

One thing to note is that I have no experience messing with APIs previously, so figuring out how to change something is difficult. My first attempt involved just replacing GET with POST and adding `role_id=3` to the body, but I was given a message that POST requests aren't allowed; PUT requests are, so I just replaced it. This sent me a response code of 200 and showed me the user information again, but nothing had changed.

Next, I tried sending it in the syntax that it was stored in:
```
{
	"role_id":3
}
```
Which, again, didn't do anything. I also tried with all of the information:
```
{
	"id":22,
	"name":"Bob",
	"email":"bob@email.com",
	"email_verified_at":null,
	"created_at":"2022-11-28T04:34:20.000000Z",
	"updated_at":"2022-11-28T04:34:20.000000Z",
	"role_id":3
}
```
Which also didn't work. I knew I was missing something, but I didn't know what. I did some research on updating APIs with PUT requests, which didn't lead to anything by itself, but I eventually found something.

One of the pages I found implied that you need to add the `Content-Type` from the response into the request's headers. I grabbed the `Content-Type` from the response and tossed it in, and tried again. This time, it worked! The response showed that the user's role ID was changed to 3. I remembered that administrators had a role ID of 1, so I did it again with a 1.

I could also change a user's grade with this. Making a request to `/api/grades/` returns a list of grades, and I can access an individual grade by adding its ID to the request (`/api/grades/1/`). Using this, I sent a new request, changing a grade from a 74 to a 100.

Looking at goal number 12, I changed the URL to end in `/admin`, which took me to an admin dashboard. I assume this would've failed if my user hadn't been changed to be an administrator. This page didn't include much, only a link to a list of security vulnerabilities that IT had recognized on the website. The only two vulnerabilities were "IDOR on most endpoints" and "Information disclosure of grades", with no other information. This wasn't very useful.

At this point I had added goals 4 (edit a student's grades),10 (find which vulnerabilities the IT admins have ignored), 11 (make your account admin), and 12 (access the admin control panel). I knew how to complete goals 14 (delete everything) and 15 (restore everything) thanks to the `/api/admin/` endpoint, but I would save that until the end. This left goals 6 (access the GraphQL API), 7 (change another account's password), and 13 (fire blind XSS in the admin control panel and validate your new admin account).

Going in order, I decided to try and access the GraphQL API. At this point I had never even heard of GraphQL, so I had to do some research. It turns out that I had already completed this goal; GraphQL was just a query language for APIs that worked in the same way as I had edited the data previously. Assuming I wasn't missing anything, I moved on.

Goal 7 was difficult. I hadn't seen any passwords at all in any of the endpoints that I had used, and I didn't know what to do. After spending some time messing around and trying to find URLs that added on to the `/admin/` URL, I went to the Contact IT button at the bottom of the home page. I submitted a few things, tried SQL injection, and so on; I didnt see anything at first.

Next, I tried something I had seen a while ago. The way that the reports work is that you enter some text, press submit, and it will print to you what you submitted. I tried `<script>test</script>`, and to my surprise, it showed a blank report, as if the script had been processed.

I didn't know anything about JavaScript scripts (and I still know very little), so I did some googling. I entered `<script>alert('hello world')</script>` and received an alert with the words hello world; it had worked.

There was one more thing I wanted to try. Back at the home page, I pressed the button to report a security vulnerability. In that section, I entered the same script as before into the issue section and submitted it. Unlike the Contact IT section, this injection was blind; at least, it would have been if I didn't have admin privileges. I visited the admin control panel and opened the list of reported issues. An alert popped up, just as I had hoped it would.

I didn't know too much about this type of attack, so I did some quick research. I found that this was a type of stored XSS, where the cross-site scripting was saved and launched when the control panel was viewed. This was cool, but because I didn't know JavaScript, I couldn't really do anything else. I was sure there was a way to get information out of this, but I would have to figure it out.