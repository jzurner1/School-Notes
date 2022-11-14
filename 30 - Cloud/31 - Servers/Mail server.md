A mail server is (usually) a collection of smaller programs that work together to process email messages.

![[Pasted image 20221016194807.png]]

Those three programs are the mail delivery agent, the mail transfer agent, and the mail user agent.

# MUA
The mail user agent is the program that interacts with the end user, allowing them to view and manipulate email messages. They don't usually run on the server and instead run on the client side.

# MTA
The mail transfer agent is responsible for both incoming and outgoing email messages on the server. For each outgoing message, the MTA determines the destination host of the recipient address. If the destination host is a remote mail server, the MVA must establish a communication link with another MTA program on the remote host to transfer the message.

There are a few MTA packages on the Linux environment, but there are three main ones:

### sendmail
The sendmail MTA package is extremely versatile and includes features such as virtual domains, message forwarding, user aliases, mail lists, and host masquerading. Unfortunately it is very complex to set up and can be too complicated for novice administrators.

### Postfix
The Postfix MTA was written as a modular application using several different programs. It is simple and uses just two small configuration files.

### Exim
The Exim MTA package sticks with the sendmail model of using one large program to handle all of the email functions. It attempts to avoid queuing messages as much as possible and instead relies on immediate delivery.

# MDA
The MDA receives messages destined for local users from the MTA program and then determines how those messages should be delivered. They can be delivered directly to the local user account or to an alternate location defined by the user, often with filters.

There are two common MDA programs used in Linux:

### Binmail
The most popular program, Binmail gets its name from the system location it is stored in (`/bin/mail`). It has become popular thanks to its simplicity. By default, it can read email messages stored in the standard `/var/spool/mail` directory or it can be pointed to an alternative mailbox.

### Procmail
Also very popular, Procmail often comes preinstalled. It is popular due to its versatility in creating user-configured recipes that allow a user to direct how the server processes received mail. A user can create a personal `.procmailrc` file in their `$HOME` directory to direct messages based on regex to separate mailbox files, forward messages to alternative email addresses, or even send messages directly to the `/dev/null` file to trash them.