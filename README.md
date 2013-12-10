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

The `//` is integer division, which returns the integer part of the division (wow).
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
'Hello, world!'
```

You can put strings together (called concatenation) with the `+` operator.

```python
>>> hello = 'Hi'
>>> world = 'World'
>>> hello + ', ' + world
'Hi, World'
```

Finally, you can get the length of a string using the `len()` function. We'll go over how functions work later. For now, know that functions work by taking an input (called an argument) inside the parentheses. For the `len()` function, the input is a string.

```python
>>> len('hello')
5
>>> pie = "I like pie"
>>> len(pie)
10
```

So this is cool, but what if you want to write a program and save it?

Writing Programs
================

Python programs have the extension `.py`. To run a program, you can go to the command line and type `python <path to file name>`. This is easier if you use the `cd` command to move to the folder containing the program.

If you write a program like we wrote above, it wouldn't do much. To make a program write output to the command prompt, you need to use the `print()` function. This works by saying `print('stuff you want to say')`. 

```python
print('Hello, world!')
print(5 + 2)
a = 5 * 2
print(a)
```

What if I want to put a comment in, though? To write text that python shouldn't evaluate, use the hashtag (`#`). Everything after the hashtag on that line will not be evaluated, which allows you to write text that says anything (usually what the line of code does).

Interacting with the user
=========================

What if we want to take input from the user? We can accomplish this with `input()`. What you put in the parentheses is what the user gets prompted with.

```python
user_input = input('Type something: ')
print('You said: ' + user_input)
```

Booleans
========

So, up until now, we've been dealing with strings, floats (decimals), integers. But what if we want to say if something is true or false? Enter booleans. To use one, you would type `True` or `False`.

```python
>>> pie = True
```

Typing: an aside
----------------

No, not keyboard typing. Python is "dynamically typed", which means that you don't have to assign the type of a variable every time you want to make one. To look at a type of an object you can use the `type()` function:

```python
>>> type('a string')
<class 'str'>
>>> type(5)
<class 'int'>
>>> type(2.5)
<class 'float'>
>>> type(True)
<class 'bool'>
```

You can also "cast" types. Casting converts the type of one object into another. To convert a string or float into an integer, use the function `int()`

```python
>>> int('5')
5
>>> int(2.5) #this doesn't round
2
```

Be careful with this, though! If you try to convert a string that isn't a number into an integer, you will get an exception, or error.

```python
>>> int('this is not a number')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'this is not a number'
```

The string representation of any object can be obtained using the `str()` function.

```python
>>> str(5)
'5'
>>> str(True)
'True'
```

The boolean value of an object can be obtained using the `bool()` function. Most objects evaluate to True, except for zeros and empty strings.

```python
>>> bool(5)
True
>>> bool(0)
False
>>> bool(0.0)
False
>>> bool('hello')
True
>>> bool('')
False
```

Finally, what if we want absolutely nothing? For that, we have `None`. If a function doesn't return anything, it actually returns None. The type of None is `NoneType`, and it evaluates to `False`.

