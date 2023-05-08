[[Privilege escalation using DLL hijacking|Similar to Windows' DLL files]], OS X is also vulnerable to dynamic library attacks. This can include several legitimate methods, but one of the most common is called dylib hijacking.

The `DYLD_INSERT_LIBRARIES` user-specific environment variable can be used to automatically load malicious libraries into a terget running process. OS X allows the loading of weak dylibs dynamically, which in turn allows an attacker to place a malicious dylib in the specified location.