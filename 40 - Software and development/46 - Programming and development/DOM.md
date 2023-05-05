The document object model (DOM) is a JavaScript representation of the HTML on a webpage. It is the exact same layout, and if something is modified on the DOM, the HTML page will change that same way, and vice versa.

The DOM and HTML are the same document in two different languages. Each HTML file has exactly one DOM.

- **Methods** are functions attached to the document object, which can do things such as allow you to select a specific HTML element. For example, there is a DOM method called `getElementById`, which allows you to access an element of a page by its ID.
- **Objects** are things like headers (`<h1>`) and paragraphs (`<p>`). Every HTML tag is an object, and the content of tags are objects as well.
- **Subobjects** are smaller objects within objects. When objects are accessed, they will return an HTML element that is an object on the DOM. This subobject will have its own methods and properties.
- **Children** are nested objects
- **Properties** are, simply, properties of an object. This may include the color of a header, the font of a paragraph, and so on.

The DOM represents HTML as a tree structure of tags:
![[Pasted image 20221208164412.png]]
When you open the inspector to look at a webpage, it shows the DOM, not the HTML.