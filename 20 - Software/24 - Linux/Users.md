# Account types
There are three main types of accounts in Linux:
- **root**: The root account is the main administrator account on a system. It has the user ID 0, and has permissions to access all files and directories on the system, regardless of any permission settings assigned.
- **Standard**: Standard Linux user accounts are used to log into a system a perform standard tasks such as running applications or shell commands. They are typically assigned a `$HOME` directory and cannot access files outside of their directory unless given permission. They usually have user IDs of over 1000.
- **Service**: Service Linux user accounts are for applications that start in the background, such as network services like the Apache web server. Their password value is an asterisk, making it so they cannot log into the system. The login shell in `/etc/passwd` is set to `nologin` to prevent command shell access. They usually have user IDs of under 1000.

# Escalating privileges
It's generally bad practice to log in as the root account to perform system related activities, as there is no accountability for who logs in with the root user account. Instead, most administrators use privilege escalation to allow their standard user account to run programs with root administrator privileges:
- **su**: The `su` command is short for substitute user. It allows a standard user account to run commands as another user account, including the root user account. This solves the problem of knowing who is performing the administrator task, but doesn't solve the problem of multiple people knowing the root password.
- **sudo**: The `sudo` command is short for substitute user do. It allows a standard user account to run any command as another user account, including the root user.
- **sudoedit**: The `sudoedit` command allows a standard user to open a file in a text editor with privileges of another user account, including the root user account.

# Restricting users
There are two main commands used to restrict users:

### ulimit
The ulimit command can be used to place specific restrictions on a user:
![[Pasted image 20221109124347.png]]

### chage
The `chage` command is used for changing password options:
![[Pasted image 20221109124437.png]]