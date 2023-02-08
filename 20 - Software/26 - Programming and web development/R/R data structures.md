There are six main data structures in R. A data structure is a collection of data stored in a specific way, accessible through a single variable.

# Important terms
- **c function**: The `c()` function is used to combine terms
- **Index number**: The index number is the position of an item in a list. For example, if an item is the third item in a list, its index number will be 3.

# Vector
A vector is a list of items that are all the same type, such as all strings or all numbers.

### Creation
To create a vector, use the `c()` function or use a colon for sequential values:
```
fruits <- c("apple", "banana", "orange")

numbers1 <- c(1, 12, 6, 14, 3)

numbers2 <- 1:10
```

### Length
To find how long a vector is, use `length()`:
```
fruits <- c("apple", "banana", "orange")

length(fruits)  # prints 3
```

### Sorting
To sort a vector either alphabetically or numerically, use `sort()`:
```
numbers1 <- c(1, 12, 6, 14, 3)

sort(numbers1)  # prints 1, 3, 6, 12, 14
```

### Retrieving items
There are a few ways to access the items within vectors. First, you can use the item's index number in square brackets:
```
fruits <- c("apple", "banana", "orange")

fruits[2]  # prints "banana"
```

Alternatively, you can access multiple items at the same time with the `c()` function:
```
fruits <- c("apple", "banana", "orange")

fruits[c(1, 3)]  # prints "apple" and "orange"
```

If you want to select every item except for one of them, use `c()` with a negative index:
```
fruits <- c("apple", "banana", "orange")

fruits[c(-1)]  # prints all except for "apple"
```

### Changing items
To change the value of a specific item within a vector, just set its index number equal to the new value:
```
fruits <- c("apple", "banana", "orange")

fruits[3] <- "grapefruit"  # replaces "orange" with "grapefruit"
```

# Lists
Lists are the same as vectors, except they can contain more than one data type.

### Creation
To create a list, use the `list()` function:
```
things <- list("yellow", 5, "spaghetti", 137)
```

### Length
To find how long a list is, use `length()`:
```
things <- list("yellow", 5, "spaghetti", 137)

length(things)  # prints 4
```

### Retrieving items
To access items in lists, you use its index number inside of square brackets:
```
things <- list("yellow", 5, "spaghetti", 137)

things[3]  # prints "spaghetti"

things[2]  # prints 5
```

