I'm learning R for various reasons, so here's my documentation.

# Variables
To declare a variable, you want to use the syntax `variableName <- value`. You can declare multiple variables this way:
```
myInt <- 35;
myString <- "Hello world!";
var1 <- var2 <- var3 <- 123;
```

### Variable manipulation
To add two numbers, use `+`:
```
int1 <- 123
int2 <- 321
int3 <- int1 + int2
```

### Data types
There are five data types in R:
- **Numbers**: Integers, fractions, and so on such as `1`, `4.6`, and `-13`
- **Integers**: Technically separate from numbers, need an `L` after the number like `3L` or `-2L`
- **Complex**: Complex numbers, require an `i` after the number such as `17i` or `-8i`
- **Character**: A string, such as `"Hello world!"` or `"11.5"`
- **Logical**: A boolean, such as `TRUE` or `FALSE`

To see a variable's data type, use `class(variableName)`.

To convert from one data type to another, use one of the following:
```
number1 <- 12
integer1 <- 15L
complex1 <- 3i

complex2 <- as.complex(number1)
number2 <- as.numeric(integer1)
integer2 <- as.integer(complex1)
```

## Strings
Besides declaring strings in the normal fashion, you can also create them using multiple lines:
```
str1 <- "abc,
def,
ghi."
```

### String functions
To find the length of a string, use `nchar(variableName)`:
```
str1 <- "Hello world!"
nchar(str1)
```
This will return a number equal to the length.

To see if a string contains another string, use `grepl(stringToFind, stringToSearch)`:
```
str1 <- "Hello world!"
grepl("He", str1)  # returns TRUE
grepl("xyz", str1)  # returns FALSE
```
This will return a boolean.

To add two strings together, use `paste(string1, string2)`:
```
str1 <- "My name is"
str2 <- "Bob"
paste(str1, str2)
```
This will return the combined string.

## Operators
**Comparison operators** can be used to compare two values. There is greater than (>), less than (<), equal to (\==), not equal to (!=), greater than or equal to (>=), and less than or equal to (<=):
```
5 > 3  # returns true
5 == 3  # returns false
5 < 3  # returns false
5 != 3  # returns true
5 >= 3  # returns true
5 <= 3  # returns false
```

There are also **mathematical operators**, including addition (+), subtraction (-), multiplication   (\*), division (/), exponents (^), modulus(%%), and integer division (%/%):
```
4 + 3  # addition, = 7
5 - 2  # subtraction, = 3
4 * 4  # multiplication, = 16
8 / 2  # division, = 4
5 %% 2  # modulus, = 1  (returns remainder)
5 %/% 2  # integer division, = 2  (division without remainder)
```
