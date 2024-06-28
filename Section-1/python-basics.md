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
- [String Operations](#String-Operations)
- [Composite Data Structures](#Basic-Data-Structures)

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
  which are then deleted after no longer being referenced by the Python garbage collector

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
float_cast = float(x)
complex_cast = complex(x,y) # 'x' for real component, 'y' for complex.
bool_cast = bool(1) # rules for bool casting later.
```

Here is some basic printing methods.
```python
# One formatting method is using the % operator. This formats string using format % values.
print('%(language)s has %(number)03d quote types.' %
      {'language': "Python", "number": 2}) # Outputs 'Python has 002 quote types.'

# You can also use f-strings.
year = 2024
name = 'George'
feels = 'Happy'
print(f'Today is {year} and {name} is {feels}.')
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
The order of operations are as follow:
- Binding or parenthesizsed expressions, i.e. (), [], {}.
- Subscription, slicing, call, attribute reference, i.e. x[index], x.attribute, x(arugments...)
- Await expressoins
- Exponentiation
- Positive, negative, bitwise NOT
- Multiplication, matrix multiplication, division, floor division, remainder
- Addition and Subtraction
- Shifts, i.e. << and >>
- Bitwise AND
- Bitwise XOR
- Bitwise OR
- Comparisons, i.e. <=, >=, ==, is not, is
- Boolean Not (not x)
- Boolean AND (and)
- Boolean OR (or)
- Conditional expression (if - else)
- Lambda expression
- Assignment expression



### Boolean
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
Here is a description of strings and methods for them.
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

# String stride
var = '01234567'
var[::2] # '0246'
var[::-2] # '7531'
var[1::2] # 1357
var[2::2] # '246'
var[::5] # '05'
var[1::-2] # '1'
var[2::-2] # '13'

# Indexing errors
char = word[42] # Error because 42 out of bounds.

# Splicing handles large indexes gracefully.
word[4:42] # Splices from 4 to end of string.
word[42:] # 42 larger than word's length, so returns ''

# Strings are immutable, reassignment doesn't work.
word[0] = 'J' # Results in error.

# Basic String methods
len(x) # returns number of characters in string.
str.split(pattern) # splits a given string by pattern. Default is space.

```

## Basic Data Structures
There are four main basic data structures in Python.
- Lists
- Tuples
- Sets
- Dictionaries

### Lists
Lists are an ordered, mutable collection that allow duplicate values. can be used
as various data structures, like arrays, linked-lists, and stacks. Here is a 
demonstration of lists.
```python
# Lists can store a variety of data types and are not type constrained.
empty_list = []
names = ['John', 'Tim', 'Anna', 'George', 1, 3, 5]

# Accesses work just like arrays in other languages.
names[0] # "John"
names[3] # "George"
names[-1] # 5
names[0] = 'Joe' 

# Splicing also works.
names[2:4] #['Anna', 'George']

# Concatenation
names2 = names + ['Eric']
names3 = names + 3 * ['Eric']

# Adding elements
names.extend([1,2]) # Extend adds each element as its own element to the end.
names.append([1,2]) # Adds a single element that is [1,2] to the end.
names.insert(2, 'Bob') # Inserts 'Bob' at index 2.

# Removing elements
del(names[0]) # Removes element at index 0.
names.remove('Tim') # removes the first instance of x in the list.
names.pop() # removes last element. Input specifies an index to remove.

# Some important functions
len(names)
names.clear() # Removes all items from the list.
names.count(x) # counts the number of times 'x' appears in names.
list.sort() # sorts the list.
list.reverse() # reverses elements in list.
list.copy() # shallow copies list.

# List comprehension is a means of creating a list in a single line.
numbers = [1, 2, 3, 4, 5]
numbers2 = [number + 1 for number in numbers]
```
For stack implementation, append and pop can be used to a stack ADT.

### Tuples
Tuples are an ordered collection, but unlike lists, they are unmutable. They 
allow for duplicate values and are used as a replacement for representing
container objects or classes which lack methods. For example, instead of
creating a song object to store song info, you can use a tuple, and order
its elements to the data structure of the song object.

Below is a demonstration of tuples.
```python
empty_tup = ()
tup1 = (1, 4, 'yes', 'false')

# Accessing works like lists.
tup[1] # 1
tup[3] # 'false'

# Splicing, Conacentation work just like lists.
# Note that tuples can't be extended or shortened after creation.

# Some important functions
len(tup1)
```
Tuples are also useful for varying inputs, such as for function inputs or
when reading data with varying sizes.
### Sets
Sets are an unordered collection type. Sets follow their mathematical property
of only storing with no duplicate elements. Some uses for sets include
membership testing, eliminating duplicates, and performing set operations.

```python
empty_set = {}
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
set1 = {'a', 'b', 'c'}
set2 = {'a', 'c', 'd'}

# Adding elements
basket.add('grape fruit')

# Removing elements
basket.remove('pear')

# Using conditionals is a common use of sets.
'apple' in basket # true
'pear' in basket # false

# Set operations.
set1 & set2 # Intersection operation: {'a', 'c'}.
set1.intersection(set2)
set1 - set2 # Difference operation: {'b'}.
set1.difference(set2)
set1 | set2 # Union operation: {'a', 'b', 'd', 'c'}.
set1.union(set2)
set1.issubset(set2) # Checks if set1 is a subset of set2.
set1 ^ set2 # Elements in Set1 and Set2 but not in both: {'d', 'b'}

# Some other operations
set([1, 2, 3]) # Turns a list into a set.
```

### Dictionaries
Dictionaries are the python implementation of "associative arrays", with 
each element coming in a pair of (key, value). Note that dicts do not contain
duplicate elements.
```python
id_dict = {'John': 1, 'Evan': 2}
# Using dict constructor.
dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])

# Accessing elements
id_dict['John'] # returns 1.

# Adding elements
id_dict['George'] = 3

# Removing elements
del[id_dict['John']]

# Keys can be used as conditionals.
'Evan' in id_dict

# Dict functions
id_dict.keys() # returns a view object of the keys as a list.
list(dict) # returns a list of the keys.
id_dict.values() # returns a view object of the values as a list.

```
TODO loops for these data structures.
