Environment variables are dynamic values that exist in every operating system. They give information about the system behavior and change the way that software and programs behave. They can be created, edited, saved, and deleted.

In essence, they act as variables that are used specifically to pass data to programs launched in shells.

For example, when you run a command, the shell will look in the directories stored in the `PATH` variable to find the command.

# Viewing environment variables
To see environment variables, you can use a few commands:
- To see all of the environment variables: `printenv`
	- Alternatively: `env`
	- Alternatively: `set`
- To see a specific variable's value: `printenv <variable name>`
	- Alternatively: `echo $<variable name>`
	- Alternatively: `env | grep <variable name>`