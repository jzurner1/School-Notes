XXE injection, short for [[XML|XML]] external entity injection, is a type of [[Injection attacks|injection attack]] that can allow an attacker to interfere with an application's processing of XML data. It can allow attackers to view files on the application server filesystem and interact with back-end systems. In some cases, it can be elevated to perform [[SSRF|SSRF]] attacks.

## XML usage
Some applications use the XML format to transmit data between the broser and the server. Applications that do this almost always use a standard library or platform API to process the XML data on the server. XXE vulnerabilities arise because the XML specification contains various potentially dangerous features, and standard parsers support these features even if they are not normally used by the applicaion.

XML external entities are a type of custom XML entity whose defined values are loaded from outside of the DTD in which they are declared. External entities allow an entity to be defined based on the contents of a file path or URL.

## Basics
There are two ways to modify submitted XML files, which in turn can be used to perform an XXE injection attack:
1. Introduce or edit a `DOCTYPE` element that define an external entity containing the path to the file
2. Edit a data value in the XML that is returned in the application's response, to make use of the defined external entity

For example, imagine a shopping application checks for the stock level of a product by submitting the following XML to the server:
```
<?xml version="1.0" encoding="UTF-8"?>
<stockCheck><productId>381</productId></stockCheck>
```
If no XXE defenses are used, this can be exploited:
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE xyz [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
<stockCheck><productId>&xxe;</productId></stockCheck>
```
The XXE payload defines an external entity `&xxe;` whose value is the contents of the `/etc/passwd` file and uses the entity within the `productId` value. This causes the application's response to include the contents of the `/etc/passwd` file.