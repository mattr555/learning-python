learning-python
===============

Syllabus and example code for HTHS's computer club introductory course


Welcome to "Learning Python", with Matthew Ramina.
@mattr555- github, twitter

This course was made with complete newbies in mind. No former knowledge of programming is required for this course.
It is intended to be taught, not read.
It implies Python 3 installed and on the $PATH.
So, without further ado, here it is:

The Interpreter
===============

Python is, first and foremost, a programming language. It is also what we call a scripting language. For those of you who have worked with compiled languages like C, Java, or .NET, there is no "Compile" button for Python. Instead, the python interpreter reads through the code and converts it to a machine-readable variation each time you run the program. This means that you can open the interpreter and run code line-by-line. The interpreter is key for testing code and figuring out what you need to write without sifting through documentation.

This makes python a good calculator. The lines that start with `>>>` are lines that one would type into the interpreter. Don't type the >>>, though! Press enter after typing each line. To run the interpreter, you can type `python` at the command line.

```python
>>> 5 + 2
7
>>> 5 - 2
3
>>> 5 * 2
10
>>> 5 / 2
2.5
```

Those commands do what you'd expect. Python also offers a better control of division:

```python
>>> 5 // 2
2
>>> 5 % 2
1
```

The `//` is integer division, which returns the integer part of the division (wow)
The `%` is called modulo or clock division. It returns the remainder of the division. This means that an easy test for an even number. `number % 2` will return 0 if the number is even, and 1 if the number is odd.

Variables
=========

What if I want to store something for future use? Python does this for you easily. You can store values (strings, numbers) in variables, and recall them later. Typing a variable at the prompt will display (print) it for you.

```python
>>> a = 1
>>> b = 2
>>> c = a + b
>>> c
3
```

Text
====

What about writing text? This is accomplished using a string. Strings are marked by quotes (either the single quote (`'`) or double quote (`"`), but don't mix them)

```python
>>> hello = 'Hello, world!'
>>> hello
Hello, world!
```

So this is cool, but what if you want to write a program and save it?

Writing Programs
================

Python programs have the extension `.py`. To run a program, you can go to the command line and type `python <path to file name>`. This is easier if you use the `cd` command to move to the folder containing the program.

If you write a program like we wrote above, it wouldn't do much. To make a program write output to the command prompt, you need to use the `print()` function. This works by saying `print('stuff you want to say')`. We'll go over how functions work later.

The quotes are not optional. The quotes tell python that what you're saying it meant to be taken literally as a string of text, not as a variable.

```python
print('Hello, world!')
print(5 + 2)
a = 5 * 2
print(a)
```

