The secure copy (SCP) utility is made for quickly transferring files in a noninteractive manner between two systems on a network using OpenSSH. It is best for small files because if it gets interrupted during operation, it cannot pick back up where it left off. For larger files, it is recommended to use rsync or sftp.

# Installation
To use scp, you need to first install the OpenSSH client. This can be done with the following commands:
- For Ubuntu/Debian: `sudo apt install -y openssh-client openssh-server`
- For CentOS/RHEL: `sudo yum install -y openssh-clients openssh`
- For Arch: `sudo pacman -Sy` and `sudo pacman -S openssh`

# Usage
The syntax is `scp [options] <source> <destination>`, but it depends on whether you want to copy files to or from your current device.

To copy files from your computer to the remote one, the `<destination>` entry will be in the format of `<username>@<hostname or IP address>:<remote path>` and the `<source>` entry will just be the local path.

To copy files to your computer from the remote one, the `<source>` entry will be in the format of `<username>@<hostname or IP address>:<remote path>` and the `<destination>` entry will just be the local path.