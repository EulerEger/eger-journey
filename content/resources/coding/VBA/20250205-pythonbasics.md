---
title: 'Python basics'
date: '2026-02-05'
draft: true
categories: ["Coding", "VBA"]
---

## Introduction

Python is a high-level programming language that is well known and widely used in science and engineering fields. It is user-friendly and allows users to interact with a computer using simple English phrases instead of complex assembly or binary commands. 

## Variables and Types

The Python ease comes from the fact that it's object-oriented, meaning you don't need to declare the variables before using them because they are objects already.

Let's explore how it works and have some fun with it. The first step is to understand the variables and types.

## Numbers :
 it can support two types of numeric variables' integer (whole numbers) and floating point (decimals) and also complex numbers. The syntax for those is ease to show.

### Integers
**Integers** are represented by the function `int()`.

{{< highlight python >}}
a = int(1)
b = int(2.5)
print(a,b)
{{< /highlight >}}
**output:**
{{< highlight text >}}
1 2
{{< /highlight >}}
### Floats
**Float** are represented by the function `float()`

{{< highlight python >}}
a = float(1)
b = float(2.5)
print(a,b)
{{< /highlight >}}
**output:**
{{< highlight text >}}
1.0 2.5
{{< /highlight >}}

### Complex
For the **complex numbers**, the function `complex()` accepts two parameters, the first is for the real part and the second one is for the imaginary part.

{{< highlight python >}}
a = complex(1)
b = complex(2,5)
print(a,b)
{{< /highlight >}}
**output:**
{{< highlight text >}}
1+0j 2+5j
{{< /highlight >}}

As shown another way to define variables is the easiest one, just write them down as it, they will be interpreted as their type.

{{< highlight python >}}
a = 1
b = 2.5
c = 3+5j
print(a, b, c)
{{< /highlight >}}
**output:**
{{< highlight text >}}
1, 2.5 3+5j
{{< /highlight >}}

## Strings
Other programming languages treats the letters and words differently, as single letter (characters/char) and words (strings). In Python, they are treated similarly as strings, which is the function for it `string()` another technic to use is to enclose them between quotation marks single (' ') and doubles(" "). The difference between the two is that using double quotes makes easy to include apostrophes.

{{< highlight python >}}
a = string(my code here)
b = "also this can be my code"
print(a, b)
{{< /highlight >}}
**output:**
{{< highlight text >}}
my code here also this can be my code
{{< /highlight >}}

We had mentioned variable definition. What does that mean in simple English? It is quite different at the math variable we all know, first Python is capital sensitive, which means that `this` and `This` are different strings, second variables must be equal to something or none, otherwise `x=` will produce an error, best practices is to set it to none `x= None`.

{{< highlight python >}}
x = None
print(x)
{{< /highlight >}}
**output:**
{{< highlight text >}}
None
{{< /highlight >}}

# Data structures

Depending on the situation, Python provides structures that allow you to access data more efficiently. For programs, accessing data is like searching for a book in a library shell, where you have to look through all the books to find the one you want, but instead of book shells is the memory allocation.

Python provides by default some data structures, they can be classified in mutable and nonmutable.

Let's start with the mutable.

## List

The list are not homogeneous dynamic arrays, which means that it can store different data types, and they can be modifiable after being created (add, remove, update, ...). As vectors in CPP they are allocated in memory closely for fast access. 

Defining a list it can be in two ways:
 - `list()` function.
 -  Writing the variables between brackets separated by commas.

{{< highlight python >}}
a = [23, 45, 12, 67, 34]
a.append(89)
a.remove(45)
print(a)
{{< /highlight >}}
**output:**
{{< highlight text >}}
[23, 12, 67, 34, 89]
{{< /highlight >}}

|Method      | Description  |
|------------|--------------|   
| `append()` | allow adding new variables to the list. |
| `remove()` | removes the firs item at the specified value. |
| `pop()`    | removes the element at the specified position. |
| `clear()`	 | Removes all the elements from the list. |
| `copy()`	 | Returns a copy of the list. |
| `count()`	 | Returns the number of elements with the specified value. |
| `extend()` | Add the elements of a list (or any iterable), to the end of the current list. |
| `index()`	 | Returns the index of the first element with the specified value. |
| `insert()` | Adds an element at the specified position. |
| `reverse()`| Reverses the order of the list. |
| `sort()`	 | Sorts the list. |

## Tuple

A tuple is an object collection separated by commas. In some ways, a tuple is similar to a list in terms of indexing, nested objects, and repetition, but a tuple is immutable, unlike list that are mutable, as list they are capable of storing all kind of variable.

Defining a list it can be in two ways:
 - `tuple()` function.
 -  Writing the variables between parentheses separated by commas.
  
{{< highlight python >}}
a = (23, 45, 12, 67, 34)
print(a)
{{< /highlight >}}
**output:**
{{< highlight text >}}
(23, 12, 67, 34, 89)
{{< /highlight >}}

|Method      | Description  |
|-----------|--------------|
| `count()`	| Returns the number of times a specified value occurs in a tuple. |
| `index()` | Searches the tuple for a specified value and returns the position of where it was found. |

## Set

A set is an unordered collection of unique elements. It is mutable, meaning you can add or remove elements (only regular sets), and it supports mathematical operations like union, intersection, and difference, they do not support duplicate variables.

Defining a list it can be in two ways:
 - `set()` function.
 -  Writing the variables between braces separated by commas.
  
{{< highlight python >}}
a = {23, 45, 12, 67, 34}
print(a)
{{< /highlight >}}
**output:**
{{< highlight text >}}
{23, 12, 67, 34, 89}
{{< /highlight >}}

To remove duplicates from lists, converting the list to set is a quick and efficient way to do so.

{{< highlight python >}}
a = [1, 2, 2, 3, 4, 4, 5]
u = set(a)
print(u)
{{< /highlight >}}
**output:**
{{< highlight text >}}
(1,2,3,4,5)
{{< /highlight >}}

| Method  | shortcut    | Description  |
|----------------|--------|------------|
| `add()`   |	|Adds an element to the set. |
| `clear()` | 	|Removes all the elements from the set. |
| `copy()`	| 	|Returns a copy of the set. |
|`difference()`|	-	|Returns a set containing the difference between two or more sets. |
|`difference_update()`| -=	| Removes the items in this set that are also included in another, specified set. |
| `discard()`|	 |	Remove the specified item. |
| `intersection()`|	&	| Returns a set, that is the intersection of two other sets.|
| `intersection_update()`| 	&=	| Removes the items in this set that are not present in other, specified set(s).|
| `isdisjoint()`|	 	|Returns whether two sets have a intersection or not. |
| `issubset()`|	<=	|Returns True if all items of this set is present in another set. |
|  	| < | 	|Returns True if all items of this set is present in another, larger set. |
| `issuperset()` |	>=	| Returns True if all items of another set is present in this set. |
| |	>	|Returns True if all items of another, smaller set is present in this set.| 
| `pop()` |	 	|Removes an element from the set.|
| `remove()` |	 |	Removes the specified element.|
| `symmetric_difference()`|	^	|Returns a set with the symmetric differences of two sets. |
| `symmetric_difference_update()`	|^=|	Inserts the symmetric differences from this set and another.|
| `union()`	|	| Return a set containing the union of sets. |
| `update()`|	=	| Update the set with the union of this set and others. |

### Set operations

Sets are ideal for performing mathematical operations like union, intersection, and difference, which are useful in fields like data analysis, database management, and computational biology.

{{< highlight python >}}
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print("Union:", a | b)
print("Intersection:", a & b)
print("Difference:", a - b)
{{< /highlight >}}
**Output:**
{{< highlight test >}}
Union: {1, 2, 3, 4, 5, 6}
Intersection: {3, 4}
Difference: {1, 2}
{{< /highlight >}}

## Dictionary

Dictionary are an ordered collection of data values, used to store data values like a map, which, unlike other Data Types that hold only a single value as an element. Dictionaries store data in key: value pairs. They are ideal for fast lookups and representing structured data. 


Defining a list it can be in two ways:
 - `dict()` function.
 -  Writing the key value follow for columns and the variable between braces separated by commas.

{{<highlight python>}}
thisdict = {
  "brand": "Ford",
  "electric": False,
  "year": 1964,
  "colors": ["red", "white", "blue"]
}
print(thisdict)
{{</highlight>}}
**Output:**
{{<highlight text>}}
{'brand': 'Ford', 'electric': False, 'year': 1964, 'colors': ['red', 'white', 'blue']}
{{</highlight>}}

|Method	| Description|
|-------|------------|
| `clear()`	| Removes all the elements from the dictionary. |
| `copy()`	| Returns a copy of the dictionary. |
| `fromkeys()`	| Returns a dictionary with the specified keys and value. |
| `get()`	| Returns the value of the specified key. |
| `items()`	| Returns a list containing a tuple for each key value pair. |
| `keys()`	| Returns a list containing the dictionary's keys. |
| `pop()`	| Removes the element with the specified key. |
| `popitem()`	| Removes the last inserted key-value pair. |
| `setdefault()`	| Returns the value of the specified key. If the key does not exist: insert the key, with the specified value. |
| `update()`	| Updates the dictionary with the specified key-value pairs. |
| `values()`	| Returns a list of all the values in the dictionary. |

# Operators

The most important functionality is the ability to perform mathematical operations. Python covers the most basic arithmetic operations.

## Arithmetic operator

{{<highlight python>}}
a = 3
b =5
print(a+b)
print(a*b)
print(a-b)
print(a/b)
{{</highlight>}}
**Output:**
{{<highlight text>}}
8
15
-2
0.6
{{</highlight>}}
Another operator available is the modulo (%) operator, which returns the integer remainder of the division:

 - a / b = c 
 - a - b*c = d

 a % b = d

{{<highlight python>}}
a = 3
b =5
a%b
{{</highlight>}}
**Output:**
{{<highlight text>}}
3
{{</highlight>}}

Using two multiplication symbols makes a power relationship.

{{<highlight python>}}
a = 3
b =5
a**b
{{</highlight>}}
**Output:**
{{<highlight text>}}
243
{{</highlight>}}

## Comparison and logic operators

In order to work with iterable there is the need to look a specific value, the comparison operator help with it, they return Booleans (True or False).


| Operator |	Name |	
|------|------|
| == 	| Equal |
| !=	| Not equal	|	
| >	    | Greater than	|	
| <	    | Less than	x < y	|
| >=	| Greater than or equal to	|	
| <=	| Less than or equal to |
| and 	| Returns True if both statements are true	|
| or	| Returns True if one of the statements is true	|
| not	| Reverse the result, returns False if the result is true |
| is 	| Returns True if both variables are the same object |	
| is not	| Returns True if both variables are not the same object |
| in 	| Returns True if a sequence with the specified value is present in the object	|
| not in	| Returns True if a sequence with the specified value is not present in the object |

### Comparison

{{<highlight python>}}
x = 5
y = 3

print(x == y)
print(x != y)
print(x > y)
print(x < y)
print(x >= y)
print(x <= y)
{{</highlight>}}
**Output:**
{{<highlight text>}}
False
True
True
False
True
False
{{</highlight>}}

### Logic

{{<highlight python>}}
x = 5
y = 3

print(x > 0 and x < 10)
print(x < 5 or x > 10)
print(not(x > 3 and x < 10))
{{</highlight>}}
**Output:**
{{<highlight text>}}
True
False
False
{{</highlight>}}

### Identity

{{<highlight python>}}
x = 5
y = 3

print(x > 0 and x < 10)
print(x < 5 or x > 10)
print(not(x > 3 and x < 10))
{{</highlight>}}
**Output:**
{{<highlight text>}}
True
False
False
{{</highlight>}}

{{<highlight python>}}
x = ["apple", "banana"]
y = ["apple", "banana"]
z = x

print(x is z)
print(x is y)
print(x == y)
print(x is not y)
{{</highlight>}}
**Output:**
{{<highlight text>}}
True
False
True
True
{{</highlight>}}

- *is* - Checks if both variables point to the same object in memory
- == - Checks if the values of both variables are equal

### Membership

{{<highlight python>}}
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)
print("pineapple" not in fruits)
{{</highlight>}}
**Output:**
{{<highlight text>}}
True
True
{{</highlight>}}

### List operation

the operators do not work in the same way in list, for example:

{{<highlight python>}}
a = [5, 3, 2, 8]
b = [6, 9, 2, 3]

print(a+b)
print(4*a)
{{</highlight>}}
**Output:**
{{<highlight text>}}
[5, 3, 2, 8, 6, 9, 2, 3]
[5, 3, 2, 8, 5, 3, 2, 8, 5, 3, 2, 8, 5, 3, 2, 8,]
{{</highlight>}}
### String

The strings are naturally lists, because they are a list of characters, the list operation will work in the same way as it does for the list.

{{<highlight python>}}
a = "hello"
b = "World"

print(a + " " + b)
print(4*a)
{{</highlight>}}
**Output:**
{{<highlight text>}}
hello world
hellohellohellohellohello
{{</highlight>}}

It is important to notice that the operation must be realized with the same data type. It will not work if you try to add a boolean with a float, although it will work between float and integer.

### String format (f-string / r-string)

The strings have two types of format structure: the raw strings (r-string) are strings that does not admit the modifiers, the backslash is treated as literal character; the formatted strings (f-string) allow embedded expressions directly inside literals using braces or argument specifiers.

%s - String (or any object with a string representation, like numbers)

%d - Integers

%f - Floating point numbers

%."number of digits"f - Floating point numbers with a fixed amount of digits to the right of the dot.

%x/%X - Integers in hex representation (lowercase/uppercase)

{{<highlight python>}}
name = "John"
age = 23
print(f"%s is %d years old." % (name, age))
{{</highlight>}}
**Output:**
{{<highlight text>}}
John is 23 years old. 
{{</highlight>}}

{{<highlight python>}}
print("C:\new\test")
print(r"C:\new\test")
{{</highlight>}}
**Output:**
{{<highlight text>}}C:
ew	est
C:\new\test
{{</highlight>}}

# Loops

Here comes the dynamic part, python presents for-loops and while-loops, the main principle is as follows:

## for-loops

For loops iterate over a given sequence, using the "range" functions is that the function returns a new list with numbers of that specified range. Note that the range function is zero based.

The `range()` function has 3 useful argument `range(start, stop, step)`

Prints out the numbers 0,1,2,3,4
{{<highlight python>}}
for x in range(5):
    print(x)
{{</highlight>}}
**Output:**
{{<highlight text>}}
0
1
2
3
4
{{</highlight>}}

Prints out 3,4,5
{{<highlight python>}}
for x in range(3, 6):
    print(x)
{{</highlight>}}
**Output:**
{{<highlight text>}}
3
4
5
{{</highlight>}}

Prints out 3,5,7
{{<highlight python>}}
for x in range(3, 8, 2):
    print(x)
{{</highlight>}}
**Output:**
{{<highlight text>}}
3
5
7
{{</highlight>}}

{{< pageview >}}