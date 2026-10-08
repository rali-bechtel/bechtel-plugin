# Python basics (study notes)

Python is an interpreted, high-level, general-purpose language. The reference
implementation, CPython, compiles source code to bytecode and then runs that
bytecode in a virtual machine.

Python is dynamically typed: a variable has no fixed type, the value does. It is
also strongly typed, so `"2" + 2` raises a TypeError instead of silently converting.

Lists are mutable and written with square brackets. Tuples are immutable and written
with parentheses. Sets hold unique elements and have no guaranteed order for indexing.
Dictionaries map keys to values, and keys must be hashable.

Indentation defines blocks. There are no curly braces for blocks. Mixing tabs and
spaces in one block can cause an IndentationError.

A function that has no return statement returns None. Default argument values are
evaluated once, when the function is defined, so a mutable default such as a list is
shared between calls.

The `==` operator compares values, while `is` compares object identity.

Python uses reference counting plus a cyclic garbage collector to free memory.
The Global Interpreter Lock (GIL) in standard CPython lets only one thread run Python
bytecode at a time, which limits CPU-bound threading but not I/O-bound threading.
