HTTP methods are used to specify the purpose of an HTTP request or response.

# GET
One of the most common methods, the GET method is used to retrieve resources. It is purely used to return those resources and it doesn't alter the data in any way.

GET requests...
- Can be cached
- Remain in the browser history
- Can be bookmarked
- Should not be used with sensitive data
- Have length restrictions
- Have their data displayed in the URL

# POST
The other most common method, the POST method is used to send data to a server to create or update a resource.

The following post request is an example of sending login information to a webpage.
![[Pasted image 20221209145835.png]]

POST requests...
- Are never cached
- Do not remain in the browser history
- Cannot be bookmarked
- Slightly safer than GET
- Have no length restrictions

# PUT
PUT is similar to POST, except that it is idempotent. This means that calling the same PUT request multiple times will produce the same result. POST requests, on the other hand, can create the same resource multiple times.

# HEAD
HEAD is identical to GET but without the response body. This is useful for checking what a GET request will return before actually making that request - good for large response bodies.

# DELETE
DELETE will delete a specified resource.

# PATCH
PATCH will apply partial modifications to a resource.

# OPTIONS
OPTIONS will ask the server to report the HTTP methods that are available for a particular resource. The server will usually respond with an `Allow` header listing the available methods.

# CONNECT
CONNECT is used to start two-way communications (tunnel) with a requested resource.

# TRACE
TRACE is used to perform a message loop-back test that tests the path for a target resource. It is designed for diagnostic purposes. The server should return the same response body contents as the request message it received. This can be used to detect side effects of proxy servers.