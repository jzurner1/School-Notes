The GUI works through three major components, the desktop environment, windows manager, and display server.

![[Pasted image 20221028110914.png]]

The window manager is a program that communicates with the display server, sometimes called a windows manager, on behalf of the UI.

The display server is a program that uses a communication protocol to transmit from the UI to the operating system and vice versa. The communication protocol is known as the display server protocol and it can operate over a network.

Another part of the display server is the compositor, which is a program that arranges various elements within a window to create a screen image to be passed back to the client's desktop.