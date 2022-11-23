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
