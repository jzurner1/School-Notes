An HTTP response is used to respond to an [[HTTP requests|HTTP request]].

![[Pasted image 20221116225255.png]]

# Status line
Similar to the request line in an HTTP request, the status line of an HTTP response always has three items. Some examples include:
`HTTP/1.1 200 OK`
`HTTP/1.1 302 FOUND`

The **HTTP version** also shows up in the request line of an HTTP request. It is almost always 1.0 or 1.1. The only notable difference between the versions is that in 1.1, the `Host` request header is mandatory.

The **HTTP status code** indicates the result of the request. `200` is the most common status code, indicating that the request was successful.

The **"reason phrase"** further describes the status of the response.

# Response headers
After the status line are the optional response headers. These provide more information about the response.

| Header         | Example value   | Description                                                    |
| -------------- | --------------- | -------------------------------------------------------------- |
| Server         | `Apache/2.2.14` | Indicates the web server software being used, may be incorrect |
| Set-Cookie     |                 | Gives the browser a cookie                                     |
| Content-Type   | `text/html`     | The format of the information being returned                   |
| Content-Length | `88`            | The length of the message body in bytes                                                               |
