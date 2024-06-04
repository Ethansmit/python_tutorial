# Python Basics

This page will look at some basics about Python, in specific, commenting, variable creation,
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
boolean = bool(1) # Boolean

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
Most objects are considered true unless if certain conditions in the class says so.
False is defined by the following:
- None or False
- 0, 0.0, 0j, Decimal(0), Fraction(0,1)
- '', (), [], {}, set(), range(0)

```python
x = True # This is considered a string literal, but can still be used for boolean operations.
x = bool(x) # Converts x to the bool type.

# Boolean operations
x and y # x && y equivalent.
x or y # x || y equivalent.
not x # Inverts the value of x. Note that not has the lowest prioerity of 'and' and 'or'.
# print(not x == y) is interpreted as print(not (x == y))

# Comparison Operators (Works just like C)
x < y
x <= y
x >= y
x == y
x != y
x is y # Object identity
x is not y # Negated object identity.
```

## String Operations
List of operations for string literals and strings.
```python
# Creation of string literal and str
word = "Hello World" # String Literal
string = str(word) # str(word, encoding=, errors=).

# Escape Characters
# Only String literals read in escape characters.
quotes = '\"That isn\'t true\"'
new_line = 'Yes\n But Why?'
# Escape characters include:
\' # Single quote
\\ # Backslash
\n # New line
\r # Carriage return
\t # Tab
\b # Backspace
\f # Form Feed
\ooo # Octal value
\xhh # Hex value

# Raw Strings, used to create string literals with escape characters.
string = r'C:\some\name' # string equals the address without escape character functionality.
print(r'Something\or\not')
# Note that raw strings cannot end with odd number of backslashes.

# Format Strings
# Formats operation, creates replacement fields with corresponding arguments indicated by {}
"It's {}".format("George") # Formats "George" into brackets.
f'The number is {5 + 3}' # Another way to use format. Useful for prints.
# Formatting can also be used for maps.
"{name} was born in {country}".format_map(name='Charles') # Formats a map entry to name and country arguments.

# Multi-line String literal
# Either ''' or """ can be used.
multi = '''\
Hello: Here are some options:
    - Option 1
    - Option 2
    - Option 3
Thanks!'''
# Note that '\' is used to remove end of line character on first line.

# String Concatenation
str1 = 'um' + 'un' # (umun)
str2 = 3 * str1 # (umunumunumun)
str3 = 'Py' 'thon' # (Python)

text = ('Put several strings within parentheses '
        'to have them joined together.')

# To join literal with variables use '+'
prefix = 'Py'
word = prefix + 'thon'

string = ('un' * 3) + 'ium'

# Indexing string
word = 'Something'
word[0] # 'S'
word[6] # 'i'

# Opposite indexing
word[-1] # 'g'
word[-6] # 'e'
# Indexes must be within length of string. Also -0 == 0.

# String splicing
word = 'Something'
word[0:3] # 'Som', Starts at word[0] and ends at word[2] (not including word[3]
word[3:5] # 'et'

word[:2] # Characters from 0 to 2 (excluded), 'So'
word[4:] # Characters from 4 (included) to end, 'thing'
word[-2:] # Characters from second last (included) to end, 'ng'

word[:4] + word[4:] # 'Something'

# Indexing errors
char = word[42] # Error because 42 out of bounds.

# Splicing handles large indexes gracefully.
word[4:42] # Splices from 4 to end of string.
word[42:] # 42 larger than word's length, so returns ''

# Strings are immutable, reassignment doesn't work.
word[0] = 'J' # Results in error.
```
Here is a list of built in functions for strings.

```python
len(word) # Length of word.
str(word) # Returns string version of object.

word.capitalize() # Returns copy of word where the first letter is capitalized and rest is lower case.
word.casefold() # Advanced lowercasing method for string comparisons.
word.lower() # Return a copy of string with all characters converted to lowercase.

word.center(20, '-') # Centers word with characters to the left nd right. Default is spaces.
word.expandtabs(tabsize) # Replaces tab characters with spaces, 'tabsize' specifies the number of spaces.
word.ljust(3," ") # Left jusitifes with the specidied width and fillchar.

word.find(sub_str, start, end) # Finds start index in word where sub_str is. Start and end can be specified.
word.index(sub_str, start, end) # Like find but raises error value if substring is not found.
word.count(sub_str,start,end) # Counts the number of times a substring appears from start to end.
word.endswith(suffix, start, end) # Checks if string ends with specified suffix. Start and end can be specified.

word.join(word2) # Returns a string concatenating word and word2.
word.encode(encoding, errors) # Returns string encoded to bytes. See encoding and error standards on Python Documentation.
word.lstrip([chars]) # Removes leading characters. The chars in argument is a string specifying the set of characters to be removed.

word.isalnum() # Returns true if the chars in the word are alphanumeric and there is atleast one character.
word.isalpha() # Returns true if all the characters are alphabetic and there is alteast on character.
word.isascii() # Returns true if all the characters are ASCII. False otherwise.
word.isdecimal() # Returns true if all the characters are decimal characters (base 10) or if word is empty.
word.isdigit() # Returns true if all characters are decimal characters and special handling characters. Must have atleast one character.
word.isidentifier() # Returns true if the string is a valid identifier according to langauge definition.
word.islower() # Return true if all characters are lowercase and there is atleast one cased character.
word.isnumeric() # Returns true if all characters are numeric characters and there is atleast one character.
word.isprintable() # Returns true if all characters are printaible or string is empty.
# Nonprintable characters are characters classified in the Unicode character database as "Other" or "Seperator"
word.isspace() # Returns true if the string is only white space and contains at least one character.
word.istitle() # Returns true if the string is titlecased and there is at least one character.
word.isupper() # Returns true if the string is uppercased and there is at least one character.
```
