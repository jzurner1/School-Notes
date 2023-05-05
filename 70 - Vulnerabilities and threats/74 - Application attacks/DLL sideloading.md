DLL sideloading is a technique that can be used to exploit vulnerabilities in software applications by using legitimate-looking [[DLL|DLL]] files in a specific location on a system.

When a Windows application needs to use a DLL file, it will search for the DLL in a specific set of directories. This includes the application's own directory, the Windows system directory, and more. Windows will search these directories in a specific order and load the first DLL with a matching name.

If a malicious DLL file with the same name as the legitimate DLL is placed in one of those directories, it may be loaded instead of the legitimate one.

To make a malicious DLL look legitimate, something called **DLL hijacking** may be used. This is where a DLL file is created with the same name and file path as the legitimate DLL, but with malicious code instead. It could also be done so that a DLL file with the same name is used, but it is placed in a directory that is searched before the legitimate DLL directory.

Once the malicious DLL is loaded, the attacker could achieve arbitrary code execution. This can be done in many ways, but there are three common methods:
1. **Hooking**, where the DLL can intercept and modify calls to legitimate functions in the application and execute its own code instead
2. **Code injection**, where the DLL can inject its own code into the application's memory space and execute it there
3. **Remote code execution**, where the DLL can establish a network connection to a remote server and download or execute additional code