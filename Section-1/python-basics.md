# Python Basics

This page will go over some basics about python, in specific, commenting, variable creation,
and a comprehensive list of functions for each data type. Note that this section will not
cover over module based data types, like decimal, it will only standard data types. I will
be brief in this section. For more information on specific functions, I would recommend
look at the [Python Documentation](https://docs.python.org/3/index.html)

Overview:
- [Commenting](#Commenting)
- [Variable Creation](#Variable-Creation)
- [Numeric Operations](#Numeric-Operations)
- [String Operations](#String-Operations)

## Commenting

Here is how to single line comment and multi-line comment
```python
# This is a single line comment.

'''
This is
A multi-line
comment
'''

"""
This is another multi-line
comment
"""
```

## Variable Creation
A few quick notes on variables.
- Variable names are case sensitive.
- Do not name variables after keywords (i.e. import, print, for, while)
- python variables do not point to specific memory, rather they point to abstracted objects,
  which are then deleted after no longer being referenced by the Python garbage collection.

```python
num = 3 # Integer
num2 = 3.0 # Float
comp = complex(3,3) # Complex

word1 = "spam eggs" # String Literal
word2 = 'spam eggs' # Another String literal, single and double quotes do the same thing.

string = str('spam eggs') # String (not literal)

null = None # Python's null

posInf = float('inf') # Infinity
negInf = float('-inf') # Negative Infinity
```
String Literals recognize escape characters, str's dont.

Here are some basic methods.
```python
print(x) # Prints given variable.
del x # Deletes variable x completely, including variable name from symbol table.
type(x) # Returns the type of variable in format <class 'type'>

# Casting
string_cast = str(x)
int_cast = int(x)
float_csat = float(x)
complex_cast = complex(x,y) # x for real component, y for complex.
```

Here are some methods for assignment.
```python
# The following do the same thing.
g = 30
h = 30
j = 30

g = h = j = 30

g, h, j = 30, 30, 30

# You can also assign different types
g, h, j = 1, 2, "Python"

# Multi line statements.
sentence = "This is a very long sentence that we want to " \
           "split over multiple lines for better readability."

# Equation on multiple lines.
sum = 1 + 2 + 3 + \
        4 + 5 + 6 + \
        7 + 8 + 9

# Implicit Continuation through the use of [], {}, or ()
numbers = [
    1, 2, 3,
    4, 5, 6,
    7, 8, 9
]

largest = max(
    3, 150,
    -35, 16
)

dictionary = {
    "name": "John Smith",
    "age": 23,
    "favorite_food": "ice cream"
}
```

## Numeric Operations

## String Operations


```python

```
