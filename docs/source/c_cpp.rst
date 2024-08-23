*****
C/C++
*****

- Q: "Cannot find xxx.h" or "ld: Cannot find libxxx" when compiling a C/C++ code?
  A: "Cannot find xxx.h" means gcc cannot find the HEADER files in the search path, and "Cannot find libxxx" means it cannot find the LIBRARY file in the path.
  Generally, there are three groups that gcc trys to find the necessary files. Ordered by priority, for the header files, gcc will try to find (1) the path
  that following the flag ``-I``, (2) the path defined by environment variable ``C_INCLUDE_PATH``, ``CPLUS_INCLUDE_PATH``, (3) and the default path
  (in general, they are ``/usr/include`` and ``/usr/local/include``); for the library files, gcc will try to find (1) the path
  that following the flag ``-L``, (2) the path defined by environment variable ``C_LIBRARY_PATH``, ``CPLUS_LIBRARY_PATH``, (3) and the default path
  (in general, they are ``/usr/lib`` and ``/usr/local/lib``). Check if the required header/library files can be found before compiling the code.

- Q: The code has passed the compiling. But get "ld: Cannot find libxxx" when executing the code?
  A: Check if the path of needed library files are in the environment variable ``LD_LIBRARY_PATH``.