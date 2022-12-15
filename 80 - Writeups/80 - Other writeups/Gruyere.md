Gruyere is an intentionally vulnerable web application similar to Altoro Mutual.

# Snippets
Gruyere lets you create blog posts that can be read by other users. I decided that this would be a good place to start.

These blog posts, called snippets, allow a bit of HTML in them. Naturally, I started with `<script>alert(1)</script>`. Putting this in a post and creating it didn't do anything; it turns out that the `<script>` tags are replaced with `<blocked>` tags, so I had to think of something else.

One payload that I've used before is `<img src="" onerror="alert(1)">`, which I plugged in and posted. This one worked; when I viewed the post, I got an alert.

Of course, `alert(1)` isn't particularly useful. It doesn't provide any proof of a vulnerability. Next, I tried `img src="" onerror="alert(document.cookie)"`, which worked as well. It provided the following information:
```
GRUYERE=108422486|bob||author; GRUYERE_ID=522263314966626391835202272668938606224
```

Next, I tried to mess around a little more. I am just learning JavaScript, so I wanted to see how the website worked. Browsing the website, I found that the username was stored in a span with the id of `menu-right`. I wanted to see if I could access that:
```
<img src="" onerror="alert(document.getElementById('menu-right').textContent)">
```
It gave the an alert with the contents:
```
Bob <bob>

| Profile
| Sign out
```
This won't be very useful for anything, but it's good practice.