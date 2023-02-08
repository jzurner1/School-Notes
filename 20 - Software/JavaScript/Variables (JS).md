# Declaring
In JavaScript, variables are declared using the `let`, `var`, or `const` keywords. They can be created with or without values, and the data type doesn't need to be declared.
```
let var1 = "Hello world!";
var var2;
const var2 = "Bob";
```

To change the value of a variable, just set it equal to its new value:
```
var1 = "Hello, world!!"
var2 = 123;
```

`var` was the original way to create variables, but it turned out to be error-prone and confusing, so `let` was created. There are some differences between the two, but either way it is recommended to use `let`.

When a variable is created with a `const`, it is immutable and cannot be changed later.

# Data types
JavaScript has a few main data types. Almost all of them are declared in the same way, regardless of their contents.

- **Numbers** include values such as `16` and `-3.5`. They can be declared with `let var1 = 5;`.
- **Strings** are the same as other languages. They can be declared with `let var2 = "Hello!";`
- **Booleans** can be `1`, `0`, `true`, or `false`. They can be declared with `let var3 = true;`
- **Arrays** contain multiple values. They can be declared with `let var4 = [1, 2, 3];`.

There are a few other data types such as objects, but I will cover them separately.

Unlike other languages, JavaScript allows you to add numbers and strings together, such as `let var1 = 13 + "hello";`. This will treat both values as strings and combine them into one string, in this case `"13hello"`.

In addition, data types are dynamic and can be changed over time. If you create a variable and set it equal to a number, you can change that variable to be equal to a string or boolean without explicitly stating it.

## Arrays
Arrays contain multiple values in a set order. They can be created in a number of ways, but usually with the `const` keyword:
```
const cities = ["Berlin", "San Diego", "Tokyo"];

const candy = new Array("Twix", "M&Ms", "Twizzlers");

const cars = [
	"Toyota",
	"Ford",
	"Nissan"
];

const laptops = [];
laptops[0] = "Dell";
laptops[1] = "Macbook";
laptops[2] = "Asus"
```

To change an array value, refer to it by its position in the array:
```
const cars[0] = "Chevrolet";
```

## Objects
An object is a structure of code that contains multiple attributes describing a single thing.

For example, you could create a `car` object that contains information about its make, model, year, and so on:
```
let car = {make:Toyota, model:Corolla, year:1997};
```
The attributes are in name:value pairs. To retrieve the information stored in the object, just do `variableName.name`, such as `car.make`.