# Python Cheatsheet

## Main
```python
if __name__ == '__main__':    # If file is not imported, this will be executed
    main()
```

### Basic and necessary commands needed to execute a well-defined python code at the command line.

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

## Getting started with the language

### I/O
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
if x<y:
  print("x is less than y)
else:
  print("x is not less than y")
```
Note that the colon (:) following <expr> is required.
Similarly, the `nested if` also works.


### Iterative statements
As other programmin languages, we have 

+ `for loop`
```python
for i in range(5):
  print(i)
```
The `range` function starts off with 0 till the number(excluded).

+ `while loop`
```python
i=0
while(i<10):
  print("{} is less than 10".format(i))
  i+=1
```
`.format()` is a type of printing.

## Data Structures

### List
```python
<list> = <list>.append(<ele>)
```
