Every program that runs on a Linux system is called a process. It can run in the foreground, meaning it will display output to a console or GUI window, or in the background, meaning it will work behind the scenes. Each process is given a special process id (PID) and the Linux system manages how processes use memory and CPU based on that PID.

To see the processes running on a Linux system, you can use the `ps` command. This will output four columns. The first column is the PID, the second is the terminal that the process was started from (TTY), the third is the CPU time that the process has used, and the fourth is the name of the process.

Alternatively, you can use the `top` command to output the processes being run in real time. It has a number of useful columns:
![[Pasted image 20221115184001.png]]
By default, the `top` command sorts based on `%CPU` value. This can be changed by pressing a specific key associated with a specific action.