# --[ C PROGRAMMING TUTORIALS

## Introduction

Widely known low-level programming language. Compiled C source code into an executable (binary).
ANSI C Standard in 1983 specifies standard library and set of functions.

To create a C program, a text editor and a compiler is needed.
* Text Editor is used to write C source code.
* Compiler is used to generate an executable from the source code if there are no errors.

A C program contains literals, variables, functions and may contain headers.
* Literals are hardcoded values in the program.
* Variables store values during computation.
* Function contains group of statements that specify computing operations to be done.
* Headers contains function declarations, macros, and data types. It must be included before use.

And every statement is terminated by a semi-colon (;)

Every C program must contain a main() function with or without arguments.
main() is a special function in C. Compiled program execution starts from the main() function.

C programs must be compiled into an executable. A compiler is used to generate the executable into
the target platform.

* GNU Compiler Collection (GCC) is a widely used C compiler.
`gcc $FLAGS $SOURCE -o $OUTPUT`

* clang has similar compiler options as gcc.
`clang $FLAGS $SOURCE -o $OUTPUT`

* Microsoft cl.exe Compiler used to compiler on windows platform. Found in Visual Studion on Windows.

Comments can be embedded in C source. Comments are ignored during compilation.
* Single line comment starts with double forward slash (//)
* Multi-line comments starts with forward slash followed by an astericks which may expand to
  multiple lines and ends with an astericks followed by a backslash (/* ... */).