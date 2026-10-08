# Quiz: Python basics

1. Python is an ______ language.
   a) assembly
   b) interpreted
   c) machine-code only
   d) markup

2. What does `"2" + 2` do in Python?
   a) returns `"22"`
   b) returns `4`
   c) raises a TypeError
   d) returns None

3. Which collection is immutable?
   a) list
   b) dictionary
   c) set
   d) tuple

4. What does a function without a `return` statement return?
   a) 0
   b) None
   c) an empty string
   d) it raises an error

5. Why is `def add(x, items=[])` risky?
   a) lists cannot be default values
   b) the default list is created once and shared between calls
   c) the default list is copied on every call
   d) Python forbids default arguments

## Answer key
1. b - Python code is run by an interpreter (CPython compiles to bytecode first).
2. c - Python is strongly typed and does not convert str and int implicitly.
3. d - Tuples cannot be changed after creation.
4. b - Without return, the result is None.
5. b - Defaults are evaluated once at definition time.
