Using [[Git|Git]] in Linux is essential for many projects.

# Setting up
After installing git, you need to set up an environment. There are three basic steps:
### 1. Create a working directory
This is as simple as creating a new directory. Make sure you create it in a folder that it can safely be kept in.
```
mkdir project
cd project
```

### 2. Initialize the .git directory
Initializing the `.git` directory is as simple as a single command:
```
git init
```

### 3. Set up repository options
If this is the first git subdirectory on your system, modify the global Git repository's configuration file to include your username and email address. This is used to track file changes:
```
git config --global user.name "<username>"
git config --global user.email "<user email>"

git config --get user.name
git config --get user.email

git config --list
```

# Committing
After an environment is established, you can begin using version control. There are four steps:
### 1. Create or modify files
This is just the process of doing something that you will want to keep track of with Git. It may be a project, program, or something else. Either way, make sure that you have some files or folders.

### 2. Add the files to the staging area
Adding files to the staging area is done with the `git add` command. Just do `git add` followed by whatever you want to add, such as `git add script.sh`. There will be no responses, so run the command `git status` to see what has happened.

To add all of the files in the current directory, you can run `git add .`.

### 3. Commit the files to the local repository
This is done with the `git commit` command. You will usually want to add the `-m` option to include a comment on the commit. For example, you can do `git commit -m "Initial commit"`.

This will commit all of the files from the staging area to the local repository. If you run `git status` again, it will tell you that there is nothing left to commit. To see a history of commits, use `git log`.

### 4. Push the files to the remote repository
Before you can push a project to a remote repository, you need to configure its address on your system. This is done with:
`git remote add origin <URL>`
If you make a mistake with the URL, you can remove it with:
`git remote rm origin`
After which you should configure the correct address. Once the URL is configured, check it with this command:
`git remote -v`
Finally, you can push the project to its location:
`git push -u origin master`