Template for a Lua libary
=========================
Library template providing boilerplate code with a fill-in-the-blanks approach. 

* can be used from Windows and *nix (API declaration)
* supports Lua 5.1 and Lua 5.2
* has default close/shutdown methods
* optional global module table (for Lua 5.1 only)

LICENSE
-------
Copyright 2012-2014, Thijs Schreijer. License is MIT/X11, the same as Lua itself

UNIX
-----
* Copy and rename the following files;
    * lua_template.c
    * lua_template.h
* Check the TODO comments in the template

WINDOWS - VISUAL STUDIO
----------------------------
The template itself can simply be copied into a solution and then
adapted for use.

Steps;

* in your solution create a new project directory
* copy the following files into that directory
    * lua_template.h
    * lua_template.c
    * lua_template.vcxproj
    * lua_template.vcxproj.filters (optional)
* Rename the 'lua_template.vcxproj' (and the .filters file)
* In visual studio add the project to your solution
* Rename the .c and .h files from within VS
* See the VS tasklist for the TODO's in the template.

Alternatively;
* use `compile.bat` from the Visual Studio/WinSDK command shell
(check the file for 'TODO' comments)


Creating Lua libraries from scratch in VS
=========================================
* Create a new project and select; Visual C++, win32, win32 project
* In the wizard select 'DLL' and 'empty project'
* Add a new C file to the project (must be done first, otherwise the C/C++ options won't show in VS2008)
* Open the new project properties (rightclick -> properties) and set
the following options;
  * C/C++, General, Additional Include Directories
      * Add the path to the Lua header files, Lua for Windows; "C:\Program Files\Lua\5.1\include"
  * C/C++, Code Generation, Runtime Libary;
      * Mutithreaded DLL (for VS2005 and before, default in 2008)
  * Linker, General, Additional Libary Directories;
      * Add the path to the Lua library files, Lua for Windows; 
        "C:\Program Files\Lua\5.1\lib"
   * Linker, Input, Additional Dependencies;
      * Add the lua51.lib files, Lua for Windows; 
        "lua51.lib"
