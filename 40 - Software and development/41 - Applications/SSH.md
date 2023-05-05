Secure shell is a protocol used to securely connect to a remote host. It is the new de facto method of remote access for devices with a CLI. It uses TCP port 22. It replaced Telnet.

To check if SSH is running, you can use `systemctl is-active sshd` followed by `systemctl is-enabled sshd`.