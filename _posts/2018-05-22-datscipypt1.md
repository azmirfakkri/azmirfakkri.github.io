---
layout: post
title: Data Science with Python, Part 1&#58; Introduction to Basics
tags: [Python, Data Science with Python]
---
This is the first post for Data Science with Python series.

Python 3 is used for all articles related to Python in my blog. Blog posts for this series are created using Jupyter Notebook.

# Introduction

Just like R, you can use Python as a calculator. But Python is versatile programming language that it can do so much more!

# Assigning Value to a Variable

In R, we usually use this sign to assign a value to a variable `<-`, but in Python, it is simply this `=`.


```python
# Assign 20 to x
x = 20

# Print x
x
```




    20



# Python Data Types

Let's learn about the data types in Python.

1. Integer - for example 20, it has no fractional part
2. Float - for example 20.50, it has an integer and fractional parts
3. String - for example 'my dogs', they are texts and need to be wrapped in a single or double quotation marks (also known as character in R)
4. Boolean - `True` or `False` (in R, these are spelled with all capital letters)
5. List

To see the data types you can simply use this function `type()`


```python
a = 20.50
b = 'my dogs'
c = True

# Check data type of x
type(x)
```




    int




```python
# Check data type of a
type(a)
```




    float




```python
# Check data type of b
type(b)
```




    str




```python
# Check data type of c
type(c)
```




    bool



## Data Conversion

In Python, you can do data conversion easily by using these functions: `int()`, `float()`, `str()` and `bool()`.
For example, when you want to print a message containing data of different types.


```python
'A trip to the vet with my dog will cost me ' + 20.50
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-37f83bf7fc93> in <module>()
    ----> 1 'A trip to the vet with my dog will cost me ' + 20.50


    TypeError: must be str, not float


I can easily fix this error by converting the float into string.


```python
'A trip to the vet with my dog will cost me €' + str(20.50)
```




    'A trip to the vet with my dog will cost me €20.5'



## List

List is another data type in Python. Just like R, list can store different types of data. A list can also contain lists.


```python
# Create a list
doggies = ['Jodi', 'Loki', 'Ru', 'Pip', 'Bear']
```


```python
# Create sublists in list
doggies = [['Jodi', 3], ['Loki', 2], ['Ru', 1], ['Pip', 2], ['Bear', 4]]
```

### Subsetting List

Different from R, in Python, the index starts at 0 and not 1.
To access the element in the list, you use `[]`. In our doggies list, we have 5 sublists.


```python
# Access first sublist
doggies[0]
```




    ['Jodi', 3]




```python
# Access second element in the first sublist
doggies[0][1]
```




    3



### Slicing List

Let's say we want to get the first, second and third sublists. We can slice the list like this `list[start:end]`.  
<span style="color:#FF0000">Important:</span> In Python, the index specified for end is not inclusive.


```python
# Get first to third sublist
doggies[0:3]
```




    [['Jodi', 3], ['Loki', 2], ['Ru', 1]]



Notice that index 3 refers to `['Pip', 2]`, but because the `end` index is not inclusive, it will not be included in the result.

### Changing Elements in List

We noticed that we made an error with Pip's age, she's not 2 but she's 3 and she has an extra p in her name! Let's changes this in our list.


```python
# Change Pip's age
doggies[3] = ['Pipp', 3]

# View updated doggies list
doggies
```




    [['Jodi', 3], ['Loki', 2], ['Ru', 1], ['Pipp', 3], ['Bear', 4]]



And we also noticed Bear is 4, when he is only a pupper!


```python
# Change Bear's age
doggies[4][1] = 1

# View updated doggies list
doggies
```




    [['Jodi', 3], ['Loki', 2], ['Ru', 1], ['Pipp', 3], ['Bear', 1]]



### Adding and Deleting Elements in List

We can easily add element to the list by using `+` sign.


```python
# Add another doggo into the list as a sublist (double bracket)
doggies = doggies + [['Fudge', 2]]

# View updated doggies list
doggies
```




    [['Jodi', 3], ['Loki', 2], ['Ru', 1], ['Pipp', 3], ['Bear', 1], ['Fudge', 2]]



Note that as we are adding another sublist, we need to use double brackets instead of single.

If we want to remove one of the sublist, we do this using `del()`.


```python
# Remove Pipp
del(doggies[3])

# View updated doggies list
doggies
```




    [['Jodi', 3], ['Loki', 2], ['Ru', 1], ['Bear', 1], ['Fudge', 2]]



### Copying a List

To copy a list (its elements), we can do it in two ways.


```python
# Using list()
doggies_copy1 = list(doggies)

# Using :
doggies_copy2 = doggies[:]
```

<span style="color:#FF0000">Important:</span> Do not copy a list like this `doggies_copy1 = doggies` as this is only copying the reference of the location of the list in your machine.

# Functions and Methods

## Difference between Function and Method

Function is a 'black box' of codes which will produce an output. In Python, everything is an object. Like string, integer and Boolean, they are objects. Function is independent of object. It can be called on different types of object in Python.

Unlike function, method is dependent on object. It can only be called on specific object. Different type of object will have different set of methods that can be used on the data passed in the method.

Let's look at a few useful functions and methods for every data type in Python.

## Functions

`len()` - finding length


```python
# Find length of doggies
len(doggies)
```




    5



`?` - To get help with any function in Python, use `?` before the function name like this `?type`

`sorted()` - sort data


```python
# Sort data alphabetically
sorted(doggies)
```




    [['Bear', 1], ['Fudge', 2], ['Jodi', 3], ['Loki', 2], ['Ru', 1]]



## Methods

### String Methods

1. `upper()` - capitalise letters
2. `count()` - count number of letters

When you want to use methods, the syntax is just very slighty different from functions. Instead of passing the object in the bracket, you do it like this, `object.method()`.


```python
# Create a variable containing string
wine = 'pinot noir'

# Capitalise letters
wine.upper()
```




    'PINOT NOIR'




```python
# Count number of n
wine.count('n')
```




    2



### List Methods

1. `index()` - find the index of the first matched element in the list
2. `count()` - find the number of appearance of an element in a list
3. `append()` - adds an element to a list
4. `remove()` - delete the first element that matches the input
5. `reverse()` - reverse the order of elements in the list


```python
# Create a list containing strings
wine_list = ['pinot noir', 'cabernet sauvignon', 'prosecco', 'malbec', 'cabernet sauvignon']

# Find the index of the first cabernet sauvignon
wine_list.index('cabernet sauvignon')
```




    1




```python
# Count number cabernet sauvignon in the list
wine_list.count('cabernet sauvignon')
```




    2




```python
# Add sauvignon blanc
wine_list.append('sauvignon blanc')

# View updated wine_list
wine_list
```




    ['pinot noir',
     'cabernet sauvignon',
     'prosecco',
     'malbec',
     'cabernet sauvignon',
     'sauvignon blanc']




```python
# Delete first matched element: cabernet sauvignon
wine_list.remove('cabernet sauvignon')

# View updated wine_list
wine_list
```




    ['pinot noir', 'prosecco', 'malbec', 'cabernet sauvignon', 'sauvignon blanc']




```python
# Reverse order
wine_list.reverse()

# View updated wine_list
wine_list
```




    ['sauvignon blanc', 'cabernet sauvignon', 'malbec', 'prosecco', 'pinot noir']



# Importing Packages

Python has a lot of useful packages that can help you with your data analysis. For example, the NumPy and pandas.
To be able to use these packages, you will need to import them.

Three things to note when importing packages:
1. You can import the whole package or import parts of the package
2. You can abbreviate the name of the packages


```python
# Import whole packages and abbreviate
import numpy as np
import pandas as pd

# Import part of a package
from matplotlib import style
```

In the second part of Data Science with Python series, we will learn two packages in detail, NumPy and Pandas.
