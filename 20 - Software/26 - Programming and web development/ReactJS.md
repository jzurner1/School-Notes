React is an open-source JavaScript library for making user interfaces. Alongside Angular and Vue, it is one of the three main JavaScript libraries that are used on the internet today. It is part of the MERN stack (MongoDB, Express, React, and Node.js), which is used to make the development process smoother.

React will update what is seen on the DOM. It doesn't do this directly like in HTML; instead, it uses virtual DOM, which is a lightweight representation of the DOM in the form of a JavaScript object. This is faster than updating the real DOM and allows the page to update just a single section instead of the whole thing.

In theory, all you need to get started is the following:
```
<html>
  <head>
    <link rel="stylesheet" href="index.css">
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
  </head>
  <body>
    <p>Hello world!</p>
    <script src="index.js" type="text/babel"></script>
  </body>
</html>
```

This will give you access to the global variables `ReactDOM`, which has many methods to it. For example, you could render some HTML to a `root` div element with the following JavaScript:
```
ReactDOM.render(<h1>Hello, world!</h1>, document.getElementById("root"));
```
