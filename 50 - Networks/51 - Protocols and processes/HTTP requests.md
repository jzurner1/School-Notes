The HTTP protocol is designed to enable communications between clients and servers, and it works as a request-response protocol for that.

For example, a client browser can send an HTTP request to the server, and the server responds to the client. The response contains status information about the request and may contain the requested content.

![[Pasted image 20221109183617.png]]

# Layout
### Header
The first line of the header is the request line, which contains the HTTP verb, the URI, and the HTTP version number. Some examples of the request line include:
`GET /home.html HTTP/1.1`
`POST /index.html HTTP/1.1`
`DELETE /query.html HTTP/1.1`

After the request line are the optional request headers. These parameters can describe specific properties about the request. They appear in name:value pairs separated by commas.

After the header is a blank line.

### Body
The body is optional and follows the blank line. It will contain any other information about the request to be sent along.

# Request headers
Most requests include a number of request headers. Some are more common than others:
| Header          | Example     | Description                                           |
| --------------- | ----------- | ----------------------------------------------------- |
| Host            | Google.com  | The domain name of the server                         |
| User-Agent      | Mozilla/5.0 | Information about how the user is making the request  |
| Accept          | text/html   | A list of acceptable data types for the response      |
| Accept-Language | en-US       | A list of acceptable human languages for the response |
| Accept-Encoding | gzip        | A list of acceptable encodings for the response       |
| Connection      | close       | Control options for the current connection            |

# GET
The GET method is used to request data from a specific resource.