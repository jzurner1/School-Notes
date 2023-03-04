# Description
This lab has an unprotected admin panel.
Solve the lab by deleting the user `carlos`.

# Process
To begin, I opened a request in Burp Intruder. I knew that the admin panel was probably just a simple directory, but I didn't know the extension, so this was my method of finding it.

`/admin` didn't work, and neither did many of the other ones I tried. Eventually, I just switched to a wordlist I found online ([this one](https://github.com/the-robot/admin-finder/blob/master/wordlist.txt)), but that didn't provide any answers either.

Next I decided to look through the site's HTML and JavaScript to see if there was anything relevant. On the login page, I noticed that the form had a hidden element:
`<input required="" type="hidden" name="csrf" value="F4BqsP1460AmWLgElpdC29zYGOJ0kivN">`
I tried enabling it and submitting the form, but nothing happened. I also plugged the value into the URL, but it wasn't successful. I tried it as the admin password, but that failed as well.

Finally, I moved on. After a couple other methods, I navigated to the `/robots.txt` file, which explicitly disallowed `/administrator-panel`. That was pretty frustrating; it turns out that the wordlist I had used contains almost every combination of `admin` and `panel`, but not that one.

I deleted the user `carlos` and finished the lab.