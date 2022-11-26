Shell scripting is a type of scripting used within Linux shells. It also works in versions of Windows and OS X.

# Introduction
### Shebangs
All shell scripts should have the following on the first line:
`#!/bin/bash`
This is called the **shebang**, which allows you to define which program will be run to interpret a script. This sets the file as a bash file. Other shebangs exist for Perl (`#!/usr/bin/perl`), Ruby (`#!/usr/bin/env ruby`), and so on.

### Running scripts
There are a couple ways to run a script. One option is with the `sh` command, where the syntax is simply `sh <script name>`. If the script has a shebang, you can change the permissions to allow it to be executed; this is done with `chmod +x <script name>`. Afterwards, you can run it with just the path, such as `./<script name>`.

### How scripts work
Scripts are basically just a list of commands. For example, if you put `echo "Hello world!"` in a script, all it will do is print `Hello world!` to the console.

# Syntax
### Functions
Functions can be called just like in other programming languages. The basic syntax is as follows:
```
<function name> () {
	<function processes>
}

<function name>  # call the function
```

### Environment variables
Environment variables track specific system information such as the name of the system, the name of the user logged into the shell, the user's UID, and more. You can get a full list of environment variables with the `set` command.

To access an environment variable within a shell script, put a `$` in front of it. For example, `$USER` will get the current user's name and `$UID` will get their UID.

### User variables
User variables are variables created within the script. You can assign variables using the equal sign without spaces, such as `var1=10` or `var2="Hello World!"`. The data type will be determined automatically.

Similar to environment variables, you can access user variables with `$`. For example, you can do `age=40` and `echo I am $age years old`. Alternatively, you can surround the variable with curly braces so you don't have to add spaces, such as `${age}`.

### Command-line arguments
When running a script, you can pass in arguments in the command line. For example, you can pass in arguments with `./scriptname.sh Bob Sally` to pass in the values `Bob` and `Sally` into the script. These can be accessed within the script with `$1` and `$2`, respectively.

### Commands as variables
You can save commands as variables. For example, the command `whoami` is the same as saving it to a variable (`var1=$(whoami)`) and calling it (`echo $var1`). When saving a command to a variable, it must be surrounded by backticks or parentheses with a dollar sign in front.

### Performing math
You can perform mathematical expressions in shell scripts using square brackets. For example, to multiply 7 and 8 in a variable, you can do `var1=[7*8]`. This only works for integers, not floating-point values.

### IF statement
If statements in shell scripts works similarly to other programming languages:
```
if [<condition>]
then
	<commands>
fi
```
Where `fi` finishes the if statement. Condition tests in shell scripts are different than other languages; they are more similar to Assembly:
![[Pasted image 20221125231946.png]]
The following command compares two values. If the first value is greater than the second, it will continue to the commands within the argument:
```
if [$1 -gt $2]
then
	<commands>
	exit
fi
```

### FOR loop
For loops work similar to other languages:
```
for <item> in <set>; do
	<commands>
done
```
For example, you could run through each file in a set:
```
for file in $(ls | sort); do
	echo This is $file
done
```

### WHILE loop
While loops use the same condition tests as if statements.
```
while [<condition>]; do
	<commands>
done
```
For example, to repeat a command while a value is greater than 0:
```
number=10
while [$number -gt 0]; do
	<commands>
	number=$[$number - 1]
done
```