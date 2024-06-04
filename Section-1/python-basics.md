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
- [Boolean Operations](#Boolean-Operations)
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
complex_cast = complex(x,y) # 'x' for real component, 'y' for complex.
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
These are operations that work with the numeric data types, specifically ints, floats, and complex values.
```python
# All numeric type supported operations.
x + y # Addition
x - y # Subtraction
x * y # Multiplication
x / y # Division (Always returns a float)
x // y # Floor Division or Integer division (discards fractional portion)
x % y # Modulo
pow(x,y) # 'x' to the power of 'y'
x ** y # Another way to write pow(x,y)
-x # Negation
+x # Unchanged
abs(x) # Absolute value
int(x) # Converts 'x' to Integer. Truncates fractional part if float.
float(x) # Converts 'x' to float.
complex(re, im) # Creates complex number with real 're' and imaginary 'im'
c.conjugate # Conjugate of complex number 'c'.
divmod # Returns the pair (x // y, x % y)

# We can also do assignment.
x += y # Note that x++ not supported
x -= y # x-- not supported
x *= y
x /= y
x //= y
x %= y

# These operations can be done on ints and floats (we will go over math module later)
math.trunc(x) # Truncates 'x' to integer.
round(x,y) # Rounds 'x' by 'y' decimal places.
math.floor(x) # Floors 'x' to nearest integer.
math.ceil(x) # Ceiling 'x' to neartest integer.

```

Integer specific operations:
```python
# Bitwise Operations on ints.
x | y # Bitwise OR of 'x' and 'y'.
x ^ y # Bitwise XOR of 'x' and 'y'.
x & y # Bitwise AND of 'x' and 'y'.
x << n # Shift 'x' left by 'n' bits.
x >> n # Shift 'x' right by 'n' bits.
~x # Invert 'x's bits.

# Other int methods.
bin(x) # Returns binary representation of 'x'.
x.bit_length() # Returns the number of bits necessary to represent 'x'.
x.bit_count() # Returns the number of 1's in binary representation.
x.to_bytes() # Returns array of bytes representing x. Input: (length, byteorder='big' or 'little', signed)
int.from_bytes(x, byteorder='big') # Returns the int representation for a byte array 'x'.
```
Float specific operations:
```python
f.as_integer_ratio() # Returns a pair of integers whose ratio is exactly equal to 'f'.
f.is_integer() # Returns true if 'f' is finite with integral value.
f.hex() # Returns the hex representation of 'f'.
float.fromhex(x) # Returns float from the given hex representation 'x'.
```

## Boolean Operations

## String Operations


```python

```
