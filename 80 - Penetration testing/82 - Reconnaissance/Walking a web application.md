Walking a web application is the process of manually reviewing it to find security issues, for testing purposes or otherwise.

- Click links and explore all the pages
	- List all the pages that have input boxes
	- List all the pages that might access a database
- Inspect element
	- Check the debugger and try break points
	- Check the network tab to see external requests
	- Search for keywords through the site, such as `admin`
- Check robots.txt
- Check sitemap.xml
- User Burp Proxy
	- Check cookies for anything dumb like `admin=false`
	- Throw in some apostrophes to check for injection