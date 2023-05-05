The HTTP protocol is designed to enable communications between clients and servers, and it works as a request-response protocol for that.

For example, a client browser can send an HTTP request to the server, and the server responds to the client. The response contains status information about the request and may contain the requested content.

![[Pasted image 20221109183617.png]]

# Request line
The first line of the header is the request line, which contains the HTTP verb, the URI, and the HTTP version number. Some examples of the request line include:
`GET /home.html HTTP/1.1`
`POST /index.html HTTP/1.1`
`DELETE /query.html HTTP/1.1`

The **HTTP verb**, also called the [[HTTP methods|HTTP method]], defines the purpose of the HTTP request. The most common verb is GET, which is used to retrieve a resource from a web server. GET requests do not have a message body.

The **URI** is just where the resource can be found, usually a URL. It is typically used as a name for the resource being requested in combination with an optional query string that follows the `?` character.

The **HTTP version** is almost always either 1.0 or 1.1. The only notable difference between the versions is that in 1.1, the `Host` request header is mandatory.

# Request headers
After the request line are the optional request headers. These parameters can describe specific properties about the request. They appear in name:value pairs separated by commas.

| Header          | Example value | Description                                                                                                           |
| --------------- | ------------- | --------------------------------------------------------------------------------------------------------------------- |
| Host            | Google.com    | The domain name of the server                                                                                         |
| User-Agent      | Mozilla/5.0   | Information about how the user is making the request. Most browsers retain the Mozilla prefix for historical reasons. |
| Accept          | text/html     | A list of acceptable data types for the response                                                                      |
| Accept-Language | en-US         | A list of acceptable human languages for the response                                                                 |
| Accept-Encoding | gzip          | A list of acceptable encodings for the response                                                                       |
| Connection      | close         | Control options for the current connection                                                                            |
| Referer         | Google.com    | Indicates the URL from where the request originated                                                                   |
| Cookie          | SessionID=xyz | Indicates cookies                                                                                                                      |

After the optional request headers is a blank line, followed by the body of the request, if it exists.