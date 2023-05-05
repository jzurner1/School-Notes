Most Windows applications do not use the fully qualified path when loading an external DLL library; instead, they first search the directory from which they have been loaded. For that reason, if an attacker can place a malicious DLL in the application directory, the application will execute the malicious DLL instead of the real DLL.

In many cases, this can be used to gain remote access to a system, or alternatively for [[Privilege escalation|privilege escalation]].

There are a few tools that can be used to detect hijackable DLLs. One of the most notable is called Robber, which can be found on GitHub.