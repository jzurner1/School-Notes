Burp Proxy is a tool within [[Burp Suite|Burp Suite]]. It can be used to intercept, inspect, and modify traffic that passes through it in either direction.

# Intercept
Intercept is the main tab on the Burp Proxy. When intercept is on, the proxy will catch all messages that pass it.

When a message is captured, there are a few controls:
- **Forward**: After you are done reviewing or editing a message, press the Forward button to send the message to its target.
- **Drop**: To cancel a message so that it never reaches its destination, use the Drop button.
- **Intercept**: Enable or disable intercept.
- **Action**: Perform a range of actions such as running scans or sending requests to other Burp tools.

# HTTP History
HTTP history will show a history of all sites (within scope) that have been visited through the proxy. This is useful if you want to go back and review previous messages.

There is a lot of information on this page:
- **#**: The request's index number
- **Host**: The protocol and server hostname
- **Method**: The HTTP method
- **URL**: The URL file path and query string
- **Params**: Shows a checkmark if the request has parameters
- **Edited**: Shows a checkmark if the request was edited by the user
- **Status**: The HTTP status code of the response
- **Length**: The length of the response in bytes
- **MIME type**: The MIME type of the response
- **Extension**: The URL's file extension
- **Title**: The page's title
- **Comment**: Any user-applied comments
- **TLS**: Shows a checkmark if TLS was used
- **IP**: The destination's IP address
- **Cookies**: Any cookies set in the response
- **Time**: The time that the request was made at
- **Listener port**: The listener port on which the request was received

Clicking on the filter button allows you to change what shows up. This can be based on almost anything that you want.

# WebSockets history
WebSockets history will show a record of any WebSocket messages that are exchanged with web servers. These communications can be viewed, intercepted, and modified for a number of purposes, such as finding vulnerabilities in WebSockets handshakes.

The following information is shown:
- **#**: The request's index number
- **URL**: The URL of the WebSocket connection
- **Direction**: Whether the message was going to the client or the server
- **Edited**: Shows a checkmark if the message was modified by the user
- **Length**: The length of the response in bytes
- **Comments**: Any user-applied comments
- **TLS**: Shows a checkmark if TLS was used
- **Time**: The time that the message was received
- **Listener port**: The listener port on which the request was received
- **WebSocket ID**: Burp's internal ID for the WebSocket that was used

WebSockets history is always updated, even if intercept is turned off. Similar to the HTTP history, WebSockets history can be filtered with the filter button.

# Options
The options tab includes options for the Burp Proxy. This can be used to change the proxy listener, how to intercept client requests and server headers, and so on. For more in-depth help, see [this page](https://portswigger.net/burp/documentation/desktop/tools/proxy/proxy-options).