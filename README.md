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
>>> 5 ** 2
25
```

Those commands do what you'd expect (`**` is for exponents). Python also offers a better control of division:

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

Variables can be reassigned. They can also be referenced in their own assignments, if they've already been assigned before.

```python
>>> a = 2
>>> a = 3
>>> a
3
>>> a = a + 2
>>> a
5
```

There are also operators for doing math and reassigning in place. `+=` adds the number to the variable and sets the variable to the new number. `a += 2` expands to `a = a + 2`. There are similar operators for the other math operations.

```python
>>> a = 3
>>> a += 2
>>> a -= 3
>>> a /= 2
>>> a *= 4
>>> a
4
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

So, up until now, we've been dealing with strings, floats (decimals), integers. But what if we want to say if something is true or false? Enter booleans. To use one, you would type `True` or `False` (case-sensitive).

```python
>>> pie = True
```

These are kind of boring, though. What if I want to compare numbers? For that, we have boolean operators:

* `==` - tests for equality
* `>` - greater than
* `<` - less than
* `>=` - greater than or equal to
* `<=` - less than or equal to
* `!=` - not equal to

For example:

```python
>>> 4 == 4
True
>>> 'hi' == 'hi'
True
>>> 4 < 3
False
>>> 4 >= 4
True
```

Control Flow
============

So far, our programs only run once, and they only go through one time. Now, lets take a look at code that makes decisions and loops.

`if`
----

`if` is used when you want to make a decision. You can use a boolean or boolean operator as described above.

```python
>>> user_input = 'hi'
>>> if user_input == 'hi':
...     print('hello there!')
...
hello there!
```

In the above example on the interpreter, you can see that the prompt changed from `>>>` to `...`. The `...` indicates that you're in a block. Blocks are indented one tab or four spaces in.

What if we want to do something when the condition is failed? For this, we have the `else` keyword. It must be used with an `if`.

```python
user_input = input('say something: ')
if user_input == 'hi':
    print('hello there!')
else:
    print('you didn\'t say "hi"')
```

Finally, what if we want to check multiple conditions? We can use `elif`, short for `else if`.

```python
user_input = input('say something: ')
if user_input == 'hi':
    print('hello there!')
elif user_input == 'hello':
    print('hai!')
else:
    print('that isn\'t something i\'m programmed to respond to')
```

Both `elif` and `else` are optional, but they must be used with an `if`.

`for`
-----

`for` is used to iterate through a list. You generally declare a variable to hold the current value of the list. In these examples, I'll use `i` (i is used a lot to signal 'item' or 'index').

```python
>>> l = [1,2,3]
>>> for i in l:
...     print(i)
...
1
2
3
```

If you just want a list of integers, though, like the above example, you can use the `range()` function. `range()` can be used in a few ways: if you use one argument `n`, it generates a list of integers from 0 to n-1. If you use two arguments, `m` and `n`, it generates a list of integers from m to n-1. If you use three arguments, `m`, `n`, and `o`, it generates a list of integers from m to n-1, counting by o.

```python
>>> for i in range(2):
...     print(i)
...
0
1
>>> for i in range(3, 5):
...     print(i)
...
3
4
>>> for i in range(5, 11, 2):
...     print(i)
...
5
7
9
```

`while`
-------

`while` is used to do something while a condition is true. It's most simple use case is `while True:`, which will continue to execute until the loop is stopped by the user. To stop execution of a python program, use `Ctrl-C` (`Cmd-C` on macs)

```python
>>> while True:
...     print("hello")
...
hello 
hello
hello
hello
hello
hello
hello
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
KeyboardInterrupt
```

You can also break out of a while loop using the keyword `break`.

```python
>>> while True:
...     user = input('Say hi: ')
...     if user == 'hi':
...         print('hello there!')
...         break
...     print('I said, say hi!')

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

