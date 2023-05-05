In Linux, all [[Processes|Processes]] have a priority value that ranges from -20 to 19. This value is used to indicate how much CPU time and memory resources it is allowed to use.

# Commands
To run a process with a custom priority, the `nice` command is used. The basic syntax is `nice -n <priority value> <command>`. To change the priority of a process that is already running, use the command `renice`, where the syntax is `renice <priority value> -p <PID(s)>`

Note: before killing a process, it is important to make sure that it has no files actively running in order to prevent corruption. This can be done with the `lsof` command.

To stop a process, you can use the `kill` command. There are a number of signals that the `kill` command can send to a process:
![[Pasted image 20221115184802.png]]
The syntax of the `kill` command is `kill [options] <PID>`, but the options block is important. You will generally use the `-s` flag, which allows you to specify what signal is sent. By default, the `TERM` signal is sent, but you can send other signals. For example, you could do `kill -s HUP <PID>` to hang up a process. The `kill` command often requires sudo permissions.

Alternatively, the `pkill` command can be used to kill processes based on their names instead of PID. For example, to kill the SSH daemon, you could run `pkill sshd`. Even more useful is the ability to run the command with wildcards: `pkill http*`, for example, will kill all processes that start with `http`.

Before running the `pkill` command, you can use the `pgrep` command to search for processes that match a query. This is useful to prevent you from stopping processes that you want to keep running.