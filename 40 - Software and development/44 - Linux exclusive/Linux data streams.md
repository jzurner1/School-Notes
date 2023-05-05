### Input vs. output
Input and output are, at their most simple, commands and command results, respectively. For example:
```
[centos@localhost ~]$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```
In the excerpt above, the `ls` command is the input and the printed contents of the directory are the output.

### Data stream types
The three types of data stream in Linux are standard input, standard output, and standard error. These names are abbreviated to be STDIN, STDOUT, and STDERR, respectively.

### STDIN (0)
Standard input comes from input devices such as the keyboard. In the example above, the `ls` command would be standard input.

### STDOUT (1)
Standard output is the result of any command. In the example above, the printed contents of the directory are the output.

### STDERR (2)
Standard error is the output of an errored command. To tell the difference between STDOUT and STDERR, run the command `echo $?`, which will print the return code of the previous command. If a 1 is printed, the last command errored and the output was standard error. If a 0 is printed, the last command was successful and the output was standard output.

### STDOUT and STDERR
Sometimes standard output and standard error can be printed at the same time. For example, when using the `find` command, all found results will be returned. However, if a directory is scanned that you don't have permission to open, it will return an error amongst the successful scans. This will give a nonzero return code, indicating an error.

If you receive both STDOUT and STDERR and want to process them separately, you can use the `2>` redirect symbol to redirect only the STDERR.
```
[centos@localhost ~]$ find /etc -type f
[centos@localhost ~]$ find /etc -type f 2> /dev/null
```
The goal of the above commands is to output all files (`-type f`) that exist in the etc directory (`/etc`). The only difference is that the second command redirects any STDERR (such as if you don't have permission to open a file) and places it into /dev/null, which is basically an instant trash can.

# Redirecting input and output
### Commands
`>` - Redirect STDOUT to a specified file. If it exists, overwrite it; if not, create it. This is the same as `1>`.
`>>` - Redirect STDOUT to a specified file. If it exists, append it; if not, create it. This is the same as `1>>`.
`2>` - Redirect STDERR to a specified file. If it exists, overwrite it; if not, create it.
`2>>` - Redirect STDERR to a specified file. If it exists, append it; if not, create it.
`&>` - Redirect STDOUT and STDERR to a specified file. If it exists, overwrite it; if not, create it.
`&&>` - Redirect STDOUT and STDERR to a specified file. If it exists, append it; if not, create it.
`<` - Redirect STDIN from a specified file into command.
`<>` - Redirect STDIN from a specified file into command and redirect STDOUT to a specified file.
`|` - Pipe the results of a command into another command

### Examples
- `echo 'Hello World' > file1.txt` - Save the phrase "Hello world" to file1.txt and overwrite anything that already exists in the file