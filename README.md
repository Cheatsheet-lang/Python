# Python Cheatsheet

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

```
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

## Third party libraries

### Pandas
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
### NLTK
```shell
$ sudo pip3 install nltk                    # Installing nltk module in Ubuntu
```
```python
import nltk

# Before trying any function download the word list
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
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