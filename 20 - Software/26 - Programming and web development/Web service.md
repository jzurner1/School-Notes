A web service is software or an application that is deployed over the internet. It uses a standard messaging protocol (such as [[SOAP|SOAP]]) to enable communication between applications developed on different platforms. For instance, Java-based services can interact with PHP applications.

### Web service architecture
A web service architecture describes the interactions among the service provider, service requester, and service registry. These interactions consist of three operations, namely publish, find, and bind. All these roles and operations work together on web service artifacts known as software modules (services) and their descriptions.
- **Service provider** - A platform that offers web services. They deploy and publish service descriptions of a web service to a service registry. Requesters find these descriptions from the service registry and use them to bind with the web service provider and invoke the web service implementation.
- **Service requester** - An application or client that is seeking a service or trying to establish communication with a service. In general, the browser is a requester, which invokes the service on behalf of a user.
- **Service registry** - The place where the provider loads service descriptions. The service requester discovers the service and retrieves binding data from the service descriptions.

There are three operations in a web service architecture:
- **Publish** - During this operation, service descriptions are published to allow the requester to discover the services
- **Find** - During this operation, the requester tries to obtain the service descriptions. This operation can be processed in two different phases: obtaining the service interface description at development time, and obtaining the binding and location description calls at run time
- **Bind** - During this operation, the requester calls and establishes communications with the services during run time, using binding data inside the service descriptions to locate and invoke the services

There are two artifacts in a web service architecture:
- **Service** - A software module offered by the service provider over the internet. It communicates with the requesters. At times, it can also serve as a reqester, invoking other services in its implementation
- **Service description** - Provides interface details and service implementation details. It consists of all the operations, network locations, binding details, datatypes, etc. It can be stored in a registry and invoked by the requester.

## Characteristics of web services
- **XML-based** - Web services use [[XML|XML]] for data representation and transportation. XML usage can avoid OS, networking, or platform binding. Applications that provide web services are highly interoperable.
- **Coarse-grained service** - In web services, some objects contain a massive amount of information and offer greater functionality than fine-grained services. A coarse-grained service is a combination of multiplae fine-grained services.
- **Loosely coupled** - Web services support a loosely coupled approach for interconnecting systems. The interaction between the systems can occur via the web API by sending XML messages. The web API incorporates a layer of abstraction for the infrastructure to make the connection flexible and adaptable.
- **Asynchronous and synchronous support** - Synchronous services are called by users who wait for a response, while asynchronous services aare called by users who do not wait for a response.
- **RPB support** - Web services support remote procedure calls (RPC) similarly to traditional applications.

## Types of web services
- **SOAP web services** - The Simple Object Access Protocol (SOAP) defines the XML format. XML is used to transfer data between the service provider and the requester. It also determines the procedure to build web services and enables data exchange between different programming languages.
- **RESTful web services** - REpresentation State Transfer (RESTful) web services are designed to make the services more productive. They use many underlying HTTP concepts to define the services. It is an architectural approach rather than a protocol like SOAP.

## Components of web service architecture:
- **UDDI** - Universal Description, Discovery, and Integration (UDDI) is a directory service that lists all the services available.
- **WSDL** - Web Services Description Language is an XML-based language that describes and traces web services.
- **WS-Security** - Web Services Security (WS-Security) plays an important role in securing web services. It is an extension of SOAP and aims to maintain the integrity and confidentiality of SOAP messages as well as to authenticate users.