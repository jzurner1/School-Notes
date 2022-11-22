Extensible markup language (XML) is a [[markup language|markup language]] and file format for storing, transmitting, and reconstructing data. It does not actually do anything, it just wraps information in tags. Software must be written to send, receive, store, or display it.

It is often used as a complement to HTML. It is used to store or transport data and HTML is used to format and display that same data.

XML does not use predefined tags like HTML does. When an XML document is created, the tags and structure are entirely made up. It is assumed the the sender, receiver, and displayer all know what tags and structure will be used.

### Basic example
The following is XML at its most basic, showing a restaurant menu:
```
<food>
	<name>Belgian Waffles</name>
	<price>$9.99</price>
	<description>
	Two of our famous Belgian Waffles with real maple syrup
	</description>
</food>
<food>
	<name>Strawberry Pancakes</name>
	<price>$12.99</price>
	<description>
	Two delicious pancakes topped with strawberries
	</description>
</food>
```

### HTML complement
When used as an HTML complement, it can include categories and ID tags. The following example is a bookstore's catalog:
```
<book category="sci-fi">
	<title lang="en">Hyperion</title>
	<author>Dan Simmons</author>
	<year>1989</year>
	<price>$8.99</year>
</book>
<book category="Computers">
	<title lang="en">The Web Application Hacker's Handbook</title>
	<author>Dafydd Stuttard, Marcus Pinto</author>
	<year>2011</year>
	<price>$30.00</price>
</book>
```