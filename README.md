# langproc-2017-cw-pie


EE2 Compiler Coursework completed during my Second Year of EIE at Imperial College

Project completed by me and my partner samstratton for as coursework

It's a compiler and a translator, able to convert C90 code into Python or compile into MIPS32 assembly. Need to use a separate linker to produce the binary (use LLVM not GNU ;) )

Not all the C90 spec is met. The following was implemented:

- All arithmetic
- Binary ops || and &&
- Comparisons such as <, >, <=, >=, == and !=
- For loops (with nesting)
- While loops (with nesting)
- Do While loops (with nesting)
- Multiple function declarations
- Function calls
- Recursion
- More than four arguments in function calls
- Simple pointers and references (ie. no double++ pointers), may have bugs. Passed some rudimentary testing
- Arrays (1D only), slightly buggy
- Unary ops
- Some more stuff I can't recall at the moment. 

The code should be clear enough to follow, I have tried to comment as much as practically needed.

Testbenches for the translator and compiler are included along with some tests.

To run the compiler tests:
    make bin/c_compiler
    ./test_compiler.sh

Assembly code is printed in the temps file, along with any errors at the sub stages in further sub-directories. Compiler tests are stored in test_deliverable/test_cases

To run the translator tests:
    make bin/c_compiler (not needed if already run for compiler tests)
    ./test_translator.sh

The translator tests are different to those of the compiler tests as not all C code translates well to Python

Translator tests in pytest, and python files produced are stored in pyres

As an aside, python tests weren't part of the project requirement hence the reduced number of tests in this area

The source folder contain two cpp files, compile and transalte which will be compiled in the makefile.

To run translate on individual tests do
    ./bin/c_compiler --translate srcfile.c -o destfile.py

To run the compiler:
    ./bin/c_compiler -S srcfile.c -o destfile.s

This runs a bash script which takes care of the running of the desired function.

To type in input via the terminal use:
    ./bin/compile 
    or
    ./bin/translate

This takes in code via stdin and prints code to stdout
