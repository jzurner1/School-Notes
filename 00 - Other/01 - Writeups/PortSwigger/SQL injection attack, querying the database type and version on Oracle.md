# Description
This lab contains an SQL injection vulnerability in the product category filter. You can use a UNION attack to retrieve the results from an injected query.

To solve the lab, display the database version string.

# Process
## The website
This website featured the names of a bunch of products as well as descriptions for them.  There wasn't anything particularly striking besides a few tabs that let you filter what products you wanted to look at. They were reflected in the URL as URL encoded strings, such as the "Food & Drink" category being reflected as `category=Food+%26+Drink`. They were also reflected on the page, with the category directly printed as the heading of the products section.

## Testing the URL
First, I plugged in some words into the URL to see what would happen. Entering the string `category=abc` just returned an empty page with no gifts. The heading of the page was changed to "abc", which was good to see.

Next, I tried an apostrophe. This returned an internal server error with no other details; nothing was returned besides that. This suggests that the shop is vulnerable to SQL injection (hence the name of the lab).

Before trying anything else, I looked up how to return the database version string. Apparently there are a couple ways to do it, so I just picked one, which was `SELECT * FROM V$VERSION`. I just needed a place to put it.

I tried plugging some things into the URL. Among others, I tried `category=SELECT+*+FROM+V$VERSION` and `category=Gifts+UNION+SELECT+*+FROM+V$VERSION`, neither of which worked.

## Trying again
At this point I decided to start over. I just needed to find a place where I could inject SQL queries, and that place was probably the URL. I had to figure out how.

Because this is an Oracle database, all queries need to be made to a table; you can't just do `UNION SELECT NULL`, you have to add `FROM <table>`. Oracle has the option to use a built-in table called `dual`, which is good for testing.

In addition, I tried to "reverse engineer" (or whatever you want to call it) the database queries. When a user enters the URL `category=Gifts`, it must take the category value and put it in a SQL query such as `SELECT * FROM Gifts`.

I tried some more queries:
- `category=Gifts+UNION+SELECT+NULL+FROM+DUAL` didn't do anything
- `category=Gifts'+UNION+SELECT+NULL+FROM+DUAL--` gave an internal server error
- `category=Gifts%27+UNION+SELECT+NULL+FROM+DUAL--` gave an internal server error

Eventually I realized that, when testing with NULL queries, you have to add more NULLs until you don't get an error. I had taken notes on it previously, but I had forgotten. I tried the query `category='+UNION+SELECT+NULL,NULL+FROM+DUAL--`, which actually didn't return an error, indicating that there are two columns.

I tried some variations of the previous queries to find the version, but nothing worked. I did some more research and found that one query to find the version is `SELECT banner FROM V$VERSION`, so I tried that as `category='+UNION+SELECT+Banner,NULL+FROM+V$VERSION--`. This one worked and solved the lab!