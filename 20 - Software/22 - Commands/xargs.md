xargs was made to allow standard input to be used as an argument in another command. It is useful in file management commands such as `rm`, `cp`, `mkdir`, and so on.

### Example 1
```
printf "File1\nFile2\nFile3" | xargs touch
```

The `xargs` command takes each line from before the pipe (in this case, the lines are File1, File2, and File3) and passes them through the `touch` command. The result of this command will be three new files named File1, File2, and File3.

### Example 2
```
ls | xargs rm
```

This command will remove every file in the current directory (listed by the `ls` command) by passing them in to the `rm` command one at a time.

### Example 3
```
printf "File1\nFile2\nFile3" | xargs -I touch {}.txt
```

This command will take the output of `printf` (File1, File2, File3) and plug them into the command `touch {}.txt`, replacing the `{}` with the respective line. The `-I` flag indicates that some text will be plugged in. The result of this command will be the creation of three files, File1.txt, File2.txt, and File3.txt.

# $() alternative
As an alternative to `xargs`, you can use `$()` with a command inside the parentheses. For example, the command `ls $(find * type -f)` will first search for files with the `find` and then list them with the `ls` command. It follows order of operations.