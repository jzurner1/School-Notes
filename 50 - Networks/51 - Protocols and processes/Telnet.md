Teletype network (telnet) is a protocol used to connect to a remote host using a terminal emulator. It provides no security. The newer alternative is SSH, which provides security. It uses TCP port 23.

Because of its simplicity, telnet can be used for other purposes. You can connect to any service and grab its banner if you want, or connect to any service running TCP without encryption.

The syntax of the command is `telnet <target IP> <port>`.

If you connect to a web server and want more information, you can send the command `GET / HTTP/1.1` for general information or `GET /<page> HTTP/1.1` for a specific page. This can tell you the server type and version, among other things.
