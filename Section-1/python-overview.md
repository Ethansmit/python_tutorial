# Python Overview

I will cover some basics about Python. Feel free to skip this right into the coding if you are not 
interested.

Overview:
- [Python Description](#A-look-at-Python)
- [Python Interpreter](#The-Python-Interpreter)
- [Installation](#Installing-Python)
- [Environment](#Python-Environments)

## A look at Python
Python is a high-level, general-purpose programming language. It is a great in between of batch-languages 
and C as it supports various coding paradigms, OOPs, functional, structured, and has great structure for 
large programs but has plenty of error checking and has high-level data types built in. It is dynamically
typed (no explicit declaration of variable types) and has garbage-collection (VERY NICE).

The design of Python emphasizes code readability through using more natural language in syntax and 
indentation over {} for scope. This usually means that Python code is much cleaner in apperance than
C and Java, as well as containing less lines of code overall. This in combination with its great error
checking makes Python a fairly easy language to learn.

The overall design philosophy of Python focuses on having a small core language with a giant library
of community made modules which gives the language its status in Software developing communities today.
Utilizing these modules is also extrodinarily simple, a simple pip installation unlocks the ability to
endless programming capabilities. The community of Python is what gives the language its power!

There are a few issues with Python which I will go over next.

Bonus: Pyhon's name is a reference to "Monty Python," an old British comedy group.

## The Python Interpreter
Python is compiled a bit different from C or Java. It is a misconception that Python doesn't compile its code,
rather the compiling is done in the background. When the Interpreter executes code, the source code is turned
into byte code, which is then ran through a virtual machine that outputs our desired results. This gives Python
the apperance of an Interpretive language, though whats going on under the hood is a bit more complicated. 

The main point about talking about the Intrepreter is that it is a main reason why implementing code on Python is 
super quick. The Python compilation and execution process has very little intermediate steps, whereas C/C++ has 
to run the code through GNN/GCC and then turn the byte code into machine code, which is created based upon specific
architectures. Having Python run through a virtual machine on byte code makes Python source code easy to transfer
and execute much faster than C/C++ or Java (little compiling time). Debugging and testing code in Python is very 
fast as a result.

Though, a noticable problem is that this method doesn't necessarily mean that the execution time of our code is fast. 
It might be quick and easy to make slight changes and run our code again, but the process of using a virtual machine
for execution instead of machine code ran directly results in Python running much slower than C/C++ or even
Java. I tell you to keep this in mind as some situations require the speed and brutal efficency of C over the 
clean and elegant Python.

Finally, because of how Python is built, it abstracts away many low-level features and operations that we are
used too in languages like C. If you are in it for system programming, this could be a deal breaker for
Python.

## Installing Python
If you are on a Linux system, Python should already be installed. Else, Windows and Mac users can go to the
official Python website located [here](https://www.python.org/) to download the executable which will
install Python. Mac users can also install Python through the terminal. You can look a tutorial up for that.

## Python Environments
Python can be ran through the terminal, open a terminal and type 'py', or it can can be used through different
Coding Environments. There are many different ways to code in Python, and because of how it executes code, it
is very easy to implement into environments like Visual Studio Code. There are various ways of coding in Python
and it is really up to you to figure out the best choice. A few recommendations is through IDLE, Python's
inbuilt environment, Visual Studio Code, or PyCharm, but of course there are many other options. Python even
as web browser-based IDEs.
