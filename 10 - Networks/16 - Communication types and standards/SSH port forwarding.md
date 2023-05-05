SSH port forwarding, also known as SSH tunneling, allows you to redirect a connection from one particular network port to port 22, where the SSH service receives it. This allows data traffic to move back and forth in a secure encrypted tunnel like a VPN.

To check if SSH is running, you can use `systemctl is-active sshd` followed by `systemctl is-enabled sshd`.

One more thing to check before attempting SSH port forwarding is the OpenSSH configuration file, `/etc/ssh/sshd_config`. Check if the value for `AllowTcpForwarding` is `yes`; if not, set it to `yes` to allow SSH port forwarding. It is okay if it is commented out as it is on by default.

There are three different kinds of SSH port forwarding.

# Local
Local port forwarding sends traffic from the OpenSSH client on your system to the client's OpenSSH server. The client's OpenSSH server then forwards that traffic onto the destination server via a secured tunnel.

In other words, outbound traffic is rerouted to a different outbound port and tunneled via OpenSSH before leaving the client system.

To set up a local connection, the `-L` argument is used with the `ssh` command.

`ssh -L local-port:127.0.0.1:remote-port -Nf user@destination-host`

- The `local-port` is the application's port number you are employing on the client side
- `127.0.0.1` designates that you are using a local SSH port forwarding method
- The `remote-port` is the port where the application is listening on the destination host
- The `user` is the desktop host username you wish to authenticate as
- The `destination-host` is the computer you are accessing remotely

This command only establishes the tunnel but does not provide the remote desktop connection. That is where the `-Nf` flags come in, with the `-N` indicating that no remote terminal process is needed and the `-f` indicating that after the user authenticates, the `ssh` command should move to the background.

# Remote
The remote SSH port forwarding method starts at the destination host rather than the client. On the destination host, you can create the tunnel with the following command:

`ssh -R local-port:127.0.0.1:remote-port -Nf user@client-host`

- The `-R` is used instead of `-L`
- The `local-port` is the port number you use on the `client-host` with the vncviewer command
- The `remote-port` is the remote desktop server
- The `client-host` is the remote client's IP address or hostname