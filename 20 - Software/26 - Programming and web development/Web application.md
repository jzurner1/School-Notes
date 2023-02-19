Web applications are software programs that run on web browsers and act as the interface between users and [[Web server|web servers]] through web pages. They enable users to request, submit, and retrieve data to and from a database over the internet by interacting through a user-friendly GUI.

Some popular web servers include [[IIS|Microsoft IIS]], [[Apache|Apache HTTP Server]], H2O, LiteSpeed, Cherokee, and so on.

## How they work

![[Pasted image 20230217155229.png]]

The main function of a web application is to fetch user-requested data from a database. When a user clicks or enters a [[URL|URL]] in a browser, the web application displays the requested content in the browser. This involves the following steps:
1. The user enters the website name or URL in the browser, after which the user's request is sent to the web server (See [[DNS process|DNS process]])
2. On receiving the request, the web server checks the file extension. If it is .HTM or .HTML, the server processes the request and sends the file to the user's browser.
	1. If it has an extension that must be processed on the server-side (such as PHP, ASP, or CFM), the web application server must process the request
	2. The web server passes the user's request to the web application server, which processes the user's request
	3. The web application server then accesses the database to perform the requested task by updating or retrieving the information stored on it
	4. After processing the request, the web application server sends the results back to the web server, which sends them back to the user's browser

## Web application architecture
Web applications run on web browsers and use a set of server-side scripts (Java, C#, Ruby, PHP, etc.) and client-side scripts ([[HTML|HTML]], [[JavaScript|JavaScript]], etc.) to execute the application. The inner workings of the web application depend on its architecture, which includes the hardware and software that perform the tasks such as reading the request as well as searching, gathering, and displaying the required data.

![[Pasted image 20230217160717.png]]

The web application architecture includes different devices, web browsers, and external web services that work with different [[Scripting|scripting]] languages to execute the web application. It consists of three layers:
1. **The client/presentation layer** - This layer includes all physical devices on the client side, such as laptops, smartphones, and computers. These devices feature operating systems and compatible browsers, which enable users to send requests for required web applications. The user requests a website by entering a URL in the browser, and the request travels to the web server. The response is eventually displayed in the form of a web page.
2. **The business logic layer** - This layer consists of two layers, the web server logic layer and the business logic layer.
	1. The **web server logic layer** contains various components such as a firewall, an HTTP request parser, a proxy caching server, and authentication and login handler, a resource handler, and a hardware component such as a server.
	2. The **business logic layer** includes the functional logic of the web application, which is implemented using technologies such as .NET, Java, and "middleware". It defines the flow of data, according to which the developer builds the application using programming languages. It stores the application data and integrates legacy applications with the latest functionality of the application. The server needs a specific protocol to access user-requested data from its database. This layer contains the software and defines the steps to search and fetch the data.
3. **The database layer** - This layer consists of [[cloud|cloud]] services, a B2B layer that holds all the commercial transactions, and a database server that supplies an organization's production data in a structured form (such as a MySQL server).