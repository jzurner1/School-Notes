In [[Python|Python]], a [[Namespace|namespace]] is used to organize the symbolic names assigned to objects. It is a collection of currently defined symbolic names along with the information about the object that each name references. You could consider them as dictionaries with key-value pairs, where the keys are object names and the values are the objects themselves.

An assignment statement, such as `x = 50`, creates a symbolic name that can be used to reference an object. In the example, `x` refers to the integer object `50`. In many programs, hundreds or thousands of these variables will be created, each pointing to a specific object in memory. This is why namespaces are important.

In Python, there are four types of namespaces, called built-in, global, enclosing, and local.

## Built-in
The built-in namespace contains the names of all of Python's built-in objects that are available at all times when Python is running. These can be listed with the command `dir(__builtins__)`.

Some notable ones include built-in functions such as `max()` and `len()` as well as object types like `int` and `str`. The Python interpreter creats the built-in namespace when it starts up, and the namespace remains in existence until the interpreter terminates.

## Global
The global namespace includes any names defined at the level of the main program. These are created when the main program body starts and remain in existence until the interpreter terminates.

Technically, there can be multiple global namespaces. The interpreter creates a global namespace for any module loaded in with the `import` statement. The `global()` function will print all of the current global names in use.

## Enclosing/enclosed
Enclosed namespaces are similar to local namespaces, but they are created in nested functions, i.e. when one function exists within another function. The function that holds the other function is the enclosing function, and the function within is the enclosed function.

In the following code, the `f()` function is the enclosing function that contains the enclosing namespace, while the `g()` function is the enclosed function:
```
f():
	g():
		...
```

## Local
A local namespace includes local names inside of a function. The namespace is created when the function is called and only lasts until the function returns.

These names are only accessible within the block of code where they are created. This includes classes, functions, and loops. The `locals()` function will print all of the current local names in use.

## LEGB rule

![[Pasted image 20230208130810.png]]

When code refers to the name of a variable, Python searches for that name in order from local namespace to built-in. For example, if your code references the variable `age`, it will go in order:
1. Local: If you refer to `age` within a function, the interpreter will first search for it in the innermost scope that's local to that function.
2. Enclosing: If `age` isn't in the local scope but appears in a function that resides inside another function, the interpreter will check the enclosing function's scope next.
3. Global: If neither the local or enclosing searches succeed, the interpreter will look in the global scope.
4. Built-in: If `age` isn't found anywhere else, the interpreter will check in the built-in scope.
5. If the name isn't found in any of these places, Python raises a `NameError` exception.