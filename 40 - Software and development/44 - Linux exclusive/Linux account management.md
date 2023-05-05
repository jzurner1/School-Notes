Adding, modifying, and removing user accounts in Linux is more difficult than in Windows, but it is an important part of system administration.

# Account configuration
Typically, the command `useradd` is used to create a new user account. There are a number of other things that must be done, however.

![[Pasted image 20221101113649.png]]

The image above shows the things involved in the account creation process. The `/etc/skel` directory is bolded because it may not be used in the process. The `/home/userid` directory may be used, may have a different name, or may not be created in the first place.

### /etc/login.defs
The `/etc/login.defs` configuration file is installed by default on most Linux distributions. It contains directives for use in various **shadow password suite** commands (an umbrella term for commands dealing with account credentials such as `useradd`).

This file controls characteristics such as password length, time between password changes, whether a home directory is created by default, and so on.

### /etc/default/useradd
The `/etc/default/useradd` configuration file has a few more directives such as the default account directory locations for accounts. It can also be accessed with the command `useradd -D`.

### /etc/skel
The `/etc/skel` directory, also known as the skeleton directory, contains files that will be moved to the home directory of new users.

### /etc/passwd
The `/etc/passwd` file stores account information, where each account's data occupies a single line in the file. When an account is created, a new record is automatically created for it in this file. An example of a record is below:

`Bob:x:1001:1001:Bob:/home/Bob:/bin/bash`

Each record contains several fields:

| Field | Example     | Description                                                          |
| ----- | ----------- | -------------------------------------------------------------------- |
| 1     | `Bob`       | Account username                                                     |
| 2     | `x`         | Used to hold password info; `x` indicates it is now in `/etc/shadow` |
| 3     | `1001`      | User identification number (UID)                                     |
| 4     | `1001`      | Group identification number (GID)                                    |
| 5     | Bob         | Comment field, optional; usually holds user's full name              |
| 6     | `/home/Bob` | User's home directory                                                |
| 7     | `/bin/bash` | User's default shell                                                                     |

Alternatively, field 7 may contain either `/sbin/nologin` or `/bin/false` as the default shell. This means that the account cannot interactively log into the system. `/sbin/nologin` is generally used for system service account records (daemons).

### /etc/shadow
The `/etc/shadow` file contains information about the account's password. Again, it holds one automatically created record for each account:

`Bob:<long hash>:17751:0:99999:7:::

Each record contains several fields:

| Field | Example       | Description                                         |
| ----- | ------------- | --------------------------------------------------- |
| 1     | `Bob`         | Account username                                    |
| 2     | `<long hash>` | Password field, salted and hashed                   |
| 3     | `17751`       | Date of last password change in epoch time          |
| 4     | `0`           | # of days until password may be changed again            |
| 5     | `99999`       | # of days until password change is required              |
| 6     | `7`           | # of days before password change a warning is given |
| 7     |               | # of days between password expiration and account deactivation            |
| 8     |               | Date of account expiration in epoch time            |
| 9     |               | Special flag, currently not used                    |

Usually epoch time is expressed in seconds, but this file expresses it in days instead.

### /etc/group
This is covered in the group management page.

# Account creation

### Checking configurations
Before creating an account, it is important to check the configurations. First, see if a home directory will be created. In general, you want to open the `/etc/login.defs` file and find the `CREATE_HOME` attribute:

`grep CREATE_HOME /etc/login.defs`

In Ubuntu distributions, this may not be set be default and you will have to manually add it in. Just add the line `CREATE_HOME yes`.

In addition, check if/where the shell directive is enabled, usually with the `useradd -D` command or `/etc/default/useradd` directory:

`useradd -D | grep SHELL`

### useradd command
Once the configurations are modified to your liking, you can create the actual account. This is done through the `useradd` command, which has a number of options to customize it as it is being created.

![[Pasted image 20221101122330.png]]

In red hat and centOS distributions, you don't really need any of them:

`useradd Bob`

In Ubuntu, you need to use a few commands:

`useradd -md /home/Bob -s /bin/bash Bob`

### Checking if it worked
Next, check to see if the proper files were created:

`grep Bob /etc/passwd`
`grep Bob /etc/shadow`
`ls -a /home/Bob`

### Passwords
Accounts don't have a password by default, so you have to set one. This can be done with the `passwd` command:

`passwd Bob`

For information about an account's password, use `chage`:

`chage -l Bob`

This can also be used to change that information:

`chage Bob`

# Changing and deleting accounts

### Changing an account
Once an account is created, it may be necessary to alter its characteristics.

The `usermod` command is useful for modifying accounts:

![[Pasted image 20221101154707.png]]

### Deleting an account
Deleting an account is pretty simple. The command is `userdel` followed by options and the username:

`userdel -r Bob`

The `-r` flag removes the home directory of the user as well.