Cisco IOS is the type of operating system used on [[Cisco Catalyst switches|Cisco switches]]. It stands for the Internetwork Operating System. This operating system defines an interface for humans called the CLI (command-line interface).

The Cisco IOS CLI allows the user to use a terminal emulation program that accepts text entered by the user. The terminal emulator sends that text to the switch, which processes the text as if it was a command. It does what the command says and may return text back to the terminal emulator.

The switch CLI can be accessed through three main methods - the console, [[Telnet|Telnet]], and [[SSH|SSH]]. Telnet and SSH use the LAN that the switch is on while the console uses a port built specifically for access to the CLI.

In this situation, the switch acts as the Telnet server while the terminal application acts as the Telnet client. While Telnet is enabled by default, more configuration is needed to actually connect to a switch.

## Modes
Telnet, SSH, and a console place the user in an area of the CLI called **user EXEC mode**, which is also called user mode. THis mode allows users to look around but makes sure that they can't break anything.

Alternatively, Cisco IOS supports the more powerful **enable mode**, also known as privileged mode or privileged EXEC mode. This gets its name from the `enable` command, which switches a user from user mode to enable mode; they can switch back with `disable`.

**Configuration mode** is the only mode that allows you to change a device's configuration. It is accessed with the `configure terminal` command and can be exited with `end`. Configuration mode can only be entered when you are in enable mode. Whenever a command is entered in configuration mode, the active configuration file will be changed immediately; it is important to be careful when entering configuration commands.

If the command prompt lists the hostname followed by a `>` (such as `user>`), it is in user mode; if the hostname is followed by a `#` (such as `user#`), it is in enable mode. In configuration mode, the prompt will list the hostname followed by `(config)#`, such as `user(config)#`.

There are actually multiple configuration modes, accessible with different commands:

![[Pasted image 20230115204658.png]]

## Security
By default, anyone can connect to the console port, change modes, or make configuration changes without any security.

Most setups use three passwords without any usernames. There is one password for console users (called the **console password**) and another password for [[Telnet|Telnet]] users (called the **vty password**). The third password is used to go into enable mode; this is called the **enable password**. The image below shows the password system:
![[Pasted image 20230119211010.png]]
To set a password, use the following checklist:
1. Set the enable password with `enable secret <value>`
2. Set the console password with:
	1. `line con 0` to enter console configuration mode
	2. `password <value>` to set the value of the console password
	3. `login` to enable console password security
3. Set the Telnet (vty) password with:
	1. `line vty 0 15` to enter vty configuration mode for all 16 vty lines (0 - 15)
	2. `password <value>` to set the value of the Telnet password
	3. `login` to enable Telnet password security