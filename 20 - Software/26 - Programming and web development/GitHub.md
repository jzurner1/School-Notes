GitHub is a web service that provides version control through [[Git|Git]]. It is the most popular Git program and provides access control, bug tracking, and more.

![[Pasted image 20230105112623.png]]

# Setting up a repository
To start a new GitHub repository, `cd` into the folder you want to use and start with the command `git init`. This is a one-time command used during setup to create a `.git` subdirectory.

Next, you can add files to the directory as needed, but preferably just a couple for the initial commit. To add them to the repository staging area, do `git add *`. To commit the staging area to the local repo, do `git commit -m "<message>"`, with the message briefly describing your changes.