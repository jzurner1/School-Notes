A dynamic link library (DLL) is a file that contains a set of functions and data, which can be used by multiple programs simultaneously. When a program needs to access a function or piece of data, it can "link" to the DLL that holds that function/data, either at runtime or when it is compiled.

## OS differences
DLLs are exclusive to [[Windows|Windows]], but other operating systems tend to have their own version. For example, Linux uses shared libraries while iOS uses dynamic libraries.

## DLL linking
As mentioned earlier, when a program needs to access a function or piece of data, it can "link" to a specific DLL. This can either be done statically or dynamically.

**Static linking** means that the program includes a copy of the DLL functions and data within its own executable at compile time. This means that the program doesn't need to load the DLL at runtime, as all the necessary content is already within the executable. This provides less dependence on other functions, but it can make the file larger and more complex.

**Dynamic linking** means that the program loads the necessary DLL functions and data at runtime, as needed. This can be done in one of two ways:
1. **Explicit linking** is when a program explicitly loads the DLL using a function like `LoadLibrary` or `GetProcAddress`, and then uses those functions and data as needed. This gives more control over when and how the DLL is loaded, but requires more code for the loading process.
2. **Implicit linking** is when the program specifies the required DLLs in its import table (a data structure used by the OS to manage dynamic linking of DLLs), and the OS automatically loads and links the DLLs when the program is launched. This makes it easier for the program to use external resources, but can be harder to debug.

