Git is a popular [[Version control|version control system]].

# Vocab
Some terms need to be understood before understanding Git:
- **Working directory**: This is where all the program files are created, modified, and reviewed. It is typically a subdirectory within the developer's home directory tree.
- **Staging area**: Also called the index, this area is located on the same system as the working directory. Program files in the working directory are registered into the staging area with the command `git add`. It has a hidden subdirectory called `.git`, which is created with the `git init` command.
- **.git/index**: The index file that contains information such as checksums, timestamps, and filenames.
- **.git/objects**: Git compresses program files and stores them as objects, also known as blobs, in this directory. If a program file is modified, it is compressed and stored as a new object. This keeps a compressed copy of each modified file.
- **Local repository**: This contains each project file's history. It also uses the `.git` subdirectory. Project tree and commit information is stored as objects in the `.git/objects` directory with the `git commit` command; this data is called a snapshot. Each commit creates a new snapshot.
- **Remote repository**: Typically a cloud-based location, this could also be another server on your local network. Common remote repositories include GitHub, GitLab, and more.

