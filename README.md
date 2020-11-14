# Python Cheatsheet

# Table of Content


<!-- vim-markdown-toc GFM -->

* [Main](#main)
* [Basic and necessary commands needed to execute a well-defined python code at the command line.](#basic-and-necessary-commands-needed-to-execute-a-well-defined-python-code-at-the-command-line)
	* [Opening a python shell.](#opening-a-python-shell)
	* [Installing a package](#installing-a-package)
	* [Running a python script](#running-a-python-script)
	* [Calculating the time of execution](#calculating-the-time-of-execution)
	* [Importing a py script](#importing-a-py-script)
* [Getting started with the language](#getting-started-with-the-language)
	* [Basic I/O](#basic-io)
	* [Variables and Constants](#variables-and-constants)
	* [Conditional Statements](#conditional-statements)
	* [Iterative statements](#iterative-statements)
	* [String formatting](#string-formatting)
* [Function](#function)
	* [Function Call](#function-call)
* [Data Structures](#data-structures)
	* [Lists](#lists)
	* [Dictionaries](#dictionaries)
	* [Tuple](#tuple)
		* [Changing Tuple Values](#changing-tuple-values)
		* [Creating tuple with one item](#creating-tuple-with-one-item)
		* [Deleting a tuple](#deleting-a-tuple)
* [Pandas](#pandas)
* [NLTK](#nltk)
* [Errors and Exceptions](#errors-and-exceptions)
	* [Exceptions](#exceptions)
* [Python Snippets](#python-snippets)
	* [Anagrams](#anagrams)
	* [Memory](#memory)
	* [Print a string N times](#print-a-string-n-times)
	* [Chunk](#chunk)
	* [Get vowels](#get-vowels)
	* [Length of Last Word in a string](#length-of-last-word-in-a-string)
	* [Valid Palindrome](#valid-palindrome)
	* [Check Lowercase](#check-lowercase)
	* [Count Negatives in a sorted Matrix](#count-negatives-in-a-sorted-matrix)
	* [Write to file](#write-to-file)
	* [Median of given array](#median-of-given-array)
	* [Even or Odd](#even-or-odd)
	* [Palindrome](#palindrome)

<!-- vim-markdown-toc -->


## Main
```python
if __name__ == '__main__':    # If file is not imported, this will be executed
    main()
```

## Basic and necessary commands needed to execute a well-defined python code at the command line.

### Opening a python shell.
```python
$ python3               
```

### Installing a package
```python
$ pip3 install <package-name>              
```

### Running a python script
```python
$ python3 <filename>.py                   
```

### Calculating the time of execution
```python 
$ time python3 <filename>.py                  
```

### Importing a py script
```python
import <filename>
```

## Getting started with the language

### Basic I/O
+ Input
```python
input("Input: ")
```
+ Output
Python automatically points the cursor to a new line.
We need not specify explicitly.
```python
print("Output")
```

### Variables and Constants
In python, we need not specify the datatype of a variable. 
The interpreter interprets the value and assigns a suitabe datatype for that.
```python
number = 0
org = "GitHub"
```

### Conditional Statements
In python, we do not write a block of code in a pair of paranthesis.
We write it after `:` followed by an indentation in the next line.

The conditional statements include `if`, `if-else`, `nested if` and so on...
```python
x,y = 0,1
if x < y:
  print("x is less than y")
else:
  print("x is not less than y")
```
Note that the colon (:) following <expr> is required.
Similarly, the `nested if` also works.


### Iterative statements
As other programming languages, we have 

+ `for loop`
```python
for i in range(5):
  print(i)
```
The `range` function starts off with 0 till the number(excluded).

+ `while loop`
```python
i=0
while(i < 10):
  print("{} is less than 10".format(i))
  i += 1
```

### String formatting
There are a few ways to format a string in Python.

+ Using the `%` operator
Strings can be formatted using the % operator:

```python
>>> foo = 'world'
>>> 'Hello %s' % foo
'Hello world'
```

To subsitute multiple instances, wrap the right hand side in a Tuple:

```python
>>> foo = 'James'
>>> bar = 'Nancy'
>>> 'Hi, my name is %s and this is %s' % (foo, bar)
'Hi, my name is James and this is Nancy'
```

You can also do variable subsitutions with a dictionary:

```python
>>> dict = { "name": "Mike", "country": "Canada" }
>>> 'I am %(name)s and I am from %(country)s' % dict
'I am Mike and I am from Canada'
```

+ `.format()`

Introduced in Python 3, but is available in Python 2.7+

```python
>>> 'Hello {}'.format('world')
'Hello world'
```

Similar to the above, subsitutions can be referred by name:

```python
>>> 'Hi {name}, your total is ${total}'.format(name='Bob', total=5.50)
'Hi Bob, your total is $5.5'
```

+ f-Strings 

Available in Python 3.6+. Works similar to the above, but is more powerful as arbitrary Python expressions can be embedded: 

```python
>>> a = 5
>>> b = 10
>>> f'Five plus ten is {a + b} and not {2 * (a + b)}.'
'Five plus ten is 15 and not 30.'
```

## Function
Function is a block of code which runs when it is called.  
Functions are declared using the `def` keyword. Function name must be a valid identifier.  
Function arguments can be literal values, variables (valid identifiers), and expressions.
```python
def sum(a, b) :
	return a + b

def subtract(a, b) :
	return a - b

def getPerson(name, age) :
	person = { "name": name, "age": age }
	return person
```

### Function Call
Functions can be called by passing the arguments according to the declaration.
```python
a = 20
b = 50
c = sum(a, b)
d = sum(b, 50)
e = subtract(b, a)
p = getPerson("Joe", 25)

# OUTPUT:
print( "Sum - {} plus {}: {}" . format( a, b, c ) ) # Sum - 20 plus 50: 70
print( "Sum - {} plus 50: {}" . format( b, d ) ) # Sum - 50 plus 50: 100
print( "Subtraction - {} minus {}: {}" . format( b, a, e ) ) # Subtraction - 50 minus 20: 30
print( "Person - {}" . format( p ) ) # Person - {'name': 'Joe', 'age': 75}
```

## Data Structures

### Lists
```python
# These are all inplace operations returns a None value

<list>.append(<ele>)            # Add an element to the end of the list
<list>.sort()                   # Sorts the given list
<list>.pop([<ele>])             # Removes the last element if no argument else removes the element at the index given
<list>.clear()                  # Makes it an empty list
<list>.insert(<index>, <ele>)   # Adds the element before the index
<list>.extend(<iterator>)
<list>.reverse()                # Reverse a given list
```

```python
# These are not inplace operations and has a return value

<list>.copy()                   # Makes a shallow copy of the list
<list>.index(<ele>)             # Returns the index of the given element
<list>.count(<ele>)             # Returns the number of occurrences of the element
```
### Dictionaries
key-value pairs.
```python
<dict> = {'Google':100, 'Facebook':80, 'Apple':90}

<dict>['Amazon'] = 85                           # Adding a key along with the value

# Accessing the dictionary 
for key in <dict>:
  print("{key} -> {x}".format(key=key, x=<dict>[key]))
 
<dict>.keys()                                   # Print all the keys
<dict>.values()                                 # Print all the values
len(<dict>)                                     # Find the length of the dictionary
<dict>.pop(<key>)                               # Removes the item with the specified key name
<dict>.copy()                                   # Make a copy of a dictionary
```
A dictionary can also contain many dictionaries, this is called nested dictionaries.

### Tuple
A tuple is a collection which is ordered, indexed and unchangeable. In Python tuples are written with round brackets.
```python
this_tuple = ('books', 'pen', 'paper')          # Defined a tuple

# Accessing Tuple Items
print(this_tuple[2])                            # paper
```

#### Changing Tuple Values
Tuples are immutable, which means they cant to changed once they are created.  
If a value inside tuple needs to be changed, the tuple must be converted to a list.  
Newly created list can be converted back to tuple after updating changes.
```python
desk_tuple = ("pen stand", "plant", "marker")
desk_list = list(desk_tuple)
desk_list[2] = "highlighter"
desk_tuple = tuple(desk_list)

print(desk_tuple[2])                            # highlighter
```

#### Creating tuple with one item
To create a tuple with only one item, you have to add a comma after the item, otherwise Python will not recognize it as a tuple.
```python
this_tuple = ("Python",)
print(type(this_tuple))                         # tuple 

# NOT a tuple
this_tuple = ("Python")
print(type(this_tuple))                         # str
```

#### Deleting a tuple
Tuples are unchangeable, so you cannot remove items from it, but you can delete the tuple completely:
```python
this_tuple = ('books', 'pen', 'paper') 
del this_tuple
print(this_tuple)                               # ERROR: this_tuple is not defined
## Third party libraries
```
## Pandas
```shell
$ sudo pip3 install pandas          # Installing pandas module in Ubuntu
```
```python
import pandas as pd

<dataframe>.head([<n>])             # Display the first n rows of the Dataframe, default value is 5 rows
<dataframe>.tail([<n>])             # Display the last n rows of the Dataframe, default value is 5 rows
<dataframe>.info()                  # Gives some information like, row and column datatypes, non-null count, and memory usage
<dataframe>.describe()              # Provides some descriptive statistics about the numerical rows in the dataframe
```
## NLTK
```shell
$ sudo pip3 install nltk                    # Installing nltk module in Ubuntu
```
```python
import nltk

# Before trying any function download the word list
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
```

## Errors and Exceptions
Program stops working on error Python raises exceptions when it encounter error.  
To avoid this, `try-catch` blocks are used.

### Exceptions
No syntax errors found, program starts execution.  
Errors detected during execution are called exceptions.  
Use try: except: finally: to catch and handle the exceptions.  
Use try: except: finally: to avoid program termination on exceptions.  
Use try: except: else: instead of try: except: finally: for alternate flows.  
Multiple except can be use to catch the exceptions.  

```python
a = 10 * (1/0)

# Throws division by zero exception and terminate the program
# Traceback (most recent call last):
  File "", line 1, in 
    a = 10 * (1/0)
# ZeroDivisionError: division by zero

# Updated Program - Valid - Try: Except: Finally
b = 10
try:
    a = 10 * (1/b)
    print( "a = {}" .format( a ) )
except:
    print( "Caught divide by zero - while getting a" )
    print( "Execute on error - b must be non-zero value" )
finally:
    print( "Execute Always - normal and exceptional flow" )

# OUTPUT
a = 1.0
Execute Always - normal and exceptional flow

## Updated Program - Error - Try: Except: Finally
b = 0
try:
    a = 10 * (1/b)
    print( "a = {}" .format( a ) )
except:
    print( "Caught divide by zero - while getting a" )
    print( "Execute on error - b must be non-zero value" )
else:
    print( "Alternate to exceptional flow" )

# Output
Caught divide by zero - while getting a
Execute on error - b must be non-zero value
Execute Always - normal and exceptional flow
```			

## Python Snippets

### Anagrams
An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.
```python
from collections import Counter
def anagram(first, second):
    return Counter(first) == Counter(second)
anagram("abcd3", "3acdb") # True
```
### Memory
This snippet can be used to check the memory usage of an object.
```python
import sys 

variable = 30 
print(sys.getsizeof(variable)) # 24
```
### Print a string N times
This snippet can be used to print a string n times without having to use loops to do it.
```python
n = 2
s ="Programming"
print(s * n) # ProgrammingProgramming
```
### Chunk
This method chunks a list into smaller lists of a specified size.
```python
def chunk(list, size):
    return [list[i:i+size] for i in range(0,len(list), size)]
```
### Get vowels
This method gets vowels (‘a’, ‘e’, ‘i’, ‘o’, ‘u’) found in a string.
```python
def get_vowels(string):
    return [each for each in string if each in 'aeiou'] 
get_vowels('foobar') # ['o', 'o', 'a']
get_vowels('gym') # []
```

### Length of Last Word in a string
This method gets the length of last word in a given string.
```python
def lengthOfLastWord(self, s: str) -> int:
        if(s.split()):
            lst=s.split()
            last=lst[-1]
            return len(last)
        return 0
```
### Valid Palindrome
This method returns a bool value specifying whether a string is palindromic or not.
```python
def isPalindrome(self, s: str) -> bool:
        s = [ x.lower() for x in s if x.isalnum() ]
        return s == s[::-1]
```
### Check Lowercase
This method checks if a string is in lower case or not.
```python
def toLowerCase(self, str):
        """
        :type str: str
        :rtype: str
        """
        return str.lower()
```
### Count Negatives in a sorted Matrix
This method returns the count of negative numbers in a sorted matrix.
```python
def countNegatives(self, grid: List[List[int]]) -> int:
        count = 0
        for num in grid:
            for n in num:
                if n < 0:
                    count += 1
        return count
```

### Write to file
This method takes in the ``name of file`` and ``content`` then write the content into the file. If the file doesn't exist then it creates the file.
```python
def write_to_file(filename, content):
  try:
    with open(filename, "w+") as f:
      f.write(content)
    print("Written to file successfully.")
  except Exception as e:
    print("Failed to write to file with error: ")
    print(e)
```
### Median of given array
This method returns the median of the given list/array as an output.
```python
import statistics
def median(arr):
    print(statistics.median(arr))
```
### Even or Odd
This function determines the given number is even or odd.
```python
def find_Evenodd(num):
    
    if(num%2==0):
        print(num," Is an even")
    else:
        print(num," is an odd")
```
### Palindrome
This function returns "yes" if given string is a palindrome, else "no". Palindrome is a string whose reverse is the string itself.
```python
def isPalindrome(s):
    if (s == s[::-1]):
        return "yes"
    else:
        return "no"
```
