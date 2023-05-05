Cross-site scripting (XSS) is a type of injection that allows an attacker to compromise the interactions that users have with an application.

### Reflected XSS
Reflected XSS is the simplest version of XSS. It shows up when an application receives data in an HTTP request and includes that data within the immediate response in an unsafe way.

For example, take the URL `www.target.com/status?message=All+systems+good` that directly displays the message onto the website, such as `All systems good`. An attacker could send the URL `www.target.com/status?message=<script>alert(1)</script>`, which will inject the script directly into the website.

### Stored XSS
Stored XSS, also known as persistent or second-order XSS is when an application receives data from a source and includes that data within its later HTTP responses.

For example, say that a message board allows users to submit posts, which are then displayed with no sanitization: `<p>This is my post!</p>`. If a script were injected, it could attack any users that read it: `<p><script>alert(1)</script></p>`.

### DOM XSS
DOM XSS, also known as DOM-based or type-0 XSS, is an XSS attack where the attack payload is executed as a result of modifying the DOM "environment" in the victim's browser used by the original client-side script. The page and the HTTP response don't change, but the client-side code contained in the page executes differently.

For example, the following code is used to create a form to let a user choose their default language, where the parameter "default" has a default language:
```
<select><script>

document.write("<OPTION value=1>"+decodeURIComponent(document.location.href.substring(document.location.href.indexOf("default=")+8))+"</OPTION>");

document.write("<OPTION value=2>English</OPTION>");

</script></select>
```
1. This page is invoked with the URL `http://target.com/page.html?default=English`. An attacker could send the following URL to a victim:
	`http://target.com/page.html?default=<script>alert(document.cookie)</script>`

2. When the victim clicks on the link, the browser sends a request for the following:
	`/page.html?default=<script>alert(document.cookie)</script>`
	to `www.target.com`.

3. The server responds to that request with the page containing the JavaScript code, and creates a DOM object for the page, in which the document.location object contains the string:
	`www.target.com/page.html?default=<script>alert(document.cookie)</script>`

4. The original JavaScript on the page doesn't expect the HTML markup, so it just puts it on the page (DOM) at runtime, where it renders and executes the script:
	`alert(document.cookie`
