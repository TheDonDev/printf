---
Custom _printf() ProjectProject Statement

The _printf project is a collaborative software engineering challenge completed by Donald Mwanga and Malcolm Mwawongo at ALX School. The objective of this project is to create a custom formatted output function in C that mimics the core architecture of the standard library's printf function found in <stdio.h>.
Our custom function, named _printf, parses a format string, dynamically processes a variable number of arguments using C's variadic handles, writes the output directly to the standard output buffer, and returns the total character byte count upon a successful lifecycle.

---

Technical Specifications & Features

Function Prototype
#C
int _printf(const char *format, ...);

Format Tag Pipeline
The parsing engine evaluates inputs by seeking the % escape token and applying formatting based on the following pattern:

Plaintext
%[flags][length]specifier

----

Supported Conversion Specifiers
Our current implementation safely handles standard man 3 printf format cases, expanding argument values appropriately into the character stream:

Specifier,Description,Example Input,Handled Output
%c,Prints a standard single character,'A',A
%s,Decodes and prints a null-terminated string,"""ALX""",ALX
%%,Escapes and prints a literal percentage sign,None,%
%d / %i,Converts and prints signed base-10 integers,-1024,-1024

-----

Operational Example
When the program executes successfully, it maps tags to arguments sequentially and tracks the return length.
int total_chars;
total_chars = _printf("Engineer: %s | Core: %c | Score: %d%%\n", "Malcolm", 'C', 100);

---

Return Value

total_chars balances out to exactly 40 (the raw count of every individual character printed to the screen, including spaces and the final newline \n).

If an invalid format pointer or parsing fault occurs, the function signals an execution crash by returning -1
