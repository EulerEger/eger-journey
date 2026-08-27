---
title: 'Data type'
date: '2026-02-05'
draft: false
categories: ["Coding", "Python"]
category_weight: 10
weight: 10
---

## Introduction

Python is a **high-level programming language** widely used in science, engineering, and many other fields. It is **user-friendly** and allows users to interact with a computer using simple, readable syntax instead of complex assembly or binary commands.

As a high-level language, Python is **more readable** than lower-level languages, which are closer to machine logic. One of Python’s key features is **dynamic typing**: variable types do not need to be declared before use. This makes the code easier to understand and debug.

Python’s ease of use comes from its **object-oriented nature**: variables are objects, so you don’t need to declare their type explicitly.

Let’s explore how **variables and data types** work in Python.

---

## Variables and Types

In Python, a **variable** is a name that refers to a value or object. Variables do not have a fixed type; instead, they refer to objects that have types. This is what makes Python **dynamically typed**.

### Assigning Variables

You can assign a value to a variable using the `=` operator.

{{< highlight python >}}  
x = 10          # Integer  
name = "Alice"  # String  
y = 3.14        # Float  
is_active = True  # Boolean  
{{< /highlight >}}

---

## Numeric Types

Python supports several numeric types: **integers**, **floating-point numbers**, and **complex numbers**.

### Integers (`int`)

**Integers** are whole numbers, positive or negative, without a decimal point.

#### Defining Integers

You can define integers directly or using the `int()` function.

{{< highlight python >}}  
a = 5  
b = int(10)  
c = int(3.9)  # Truncates to 3  
print(a, b, c)  # Output: 5 10 3  
{{< /highlight >}}

#### Common Operations on Integers


| Operation      | Example   | Description                        |
| -------------- | --------- | ---------------------------------- |
| Addition       | `5 + 3`   | Returns `8`.                       |
| Subtraction    | `10 - 4`  | Returns `6`.                       |
| Multiplication | `3 * 4`   | Returns `12`.                      |
| Division       | `10 / 2`  | Returns `5.0` (float).             |
| Floor Division | `10 // 3` | Returns `3` (integer division).    |
| Modulus        | `10 % 3`  | Returns `1` (remainder).           |
| Exponentiation | `2 ** 3`  | Returns `8` (2 to the power of 3). |


#### Common Integer Methods


| Method         | Example            | Description                                                                       |
| -------------- | ------------------ | --------------------------------------------------------------------------------- |
| `bit_length()` | `(5).bit_length()` | Returns the number of bits required to represent the integer in binary (3 for 5). |


---

### Floating-Point Numbers (`float`)

**Floating-point numbers** (or **floats**) are numbers with a decimal point or in exponential form.

#### Defining Floats

You can define floats directly or using the `float()` function.

{{< highlight python >}}  
a = 3.14  
b = float(5)  
c = float("3.14")  
print(a, b, c)  # Output: 3.14 5.0 3.14  
{{< /highlight >}}

#### Common Operations on Floats


| Operation      | Example      | Description         |
| -------------- | ------------ | ------------------- |
| Addition       | `3.14 + 2.5` | Returns `5.64`.     |
| Subtraction    | `5.5 - 2.3`  | Returns `3.2`.      |
| Multiplication | `2.5 * 4`    | Returns `10.0`.     |
| Division       | `10.0 / 3`   | Returns `3.333...`. |


#### Common Float Methods


| Method               | Example                     | Description                                                       |
| -------------------- | --------------------------- | ----------------------------------------------------------------- |
| `is_integer()`       | `(5.0).is_integer()`        | Returns `True` if the float is an integer (5.0 is 5).             |
| `as_integer_ratio()` | `(3.14).as_integer_ratio()` | Returns a tuple of integers representing the float as a fraction. |


---

### Complex Numbers (`complex`)

**Complex numbers** are numbers with a real and an imaginary part, written as `a + bj` where `a` is the real part and `b` is the imaginary part.

#### Defining Complex Numbers

You can define complex numbers using the `complex()` function or directly.

{{< highlight python >}}  
a = complex(2, 3)  # 2 + 3j  
b = 1 + 2j  
print(a, b)  # Output: (2+3j) (1+2j)  
{{< /highlight >}}

#### Common Operations on Complex Numbers


| Operation      | Example              | Description         |
| -------------- | -------------------- | ------------------- |
| Addition       | `(1+2j) + (3+4j)`    | Returns `(4+6j)`.   |
| Subtraction    | `(5+6j) - (2+3j)`    | Returns `(3+3j)`.   |
| Multiplication | `(1+2j) * (3+4j)`    | Returns `(-5+10j)`. |
| Conjugate      | `(1+2j).conjugate()` | Returns `(1-2j)`.   |


#### Common Complex Number Attributes


| Attribute | Example       | Description                         |
| --------- | ------------- | ----------------------------------- |
| `real`    | `(1+2j).real` | Returns the real part (`1.0`).      |
| `imag`    | `(1+2j).imag` | Returns the imaginary part (`2.0`). |


---

## Boolean Type (`bool`)

The **boolean type** (`bool`) represents the truth values `True` and `False`. Booleans are often used in conditional statements and comparisons.

### Defining Booleans

{{< highlight python >}}  
is_active = True  
is_empty = False  
{{< /highlight >}}

### Common Operations on Booleans


| Operation | Example          | Description      |
| --------- | ---------------- | ---------------- |
| `and`     | `True and False` | Returns `False`. |
| `or`      | `True or False`  | Returns `True`.  |
| `not`     | `not True`       | Returns `False`. |


---

## String Type (`str`)

**Strings** are sequences of Unicode characters, used to represent text. They are **immutable**.

### Defining Strings

You can define strings using single quotes (`'`), double quotes (`"`), or triple quotes (`'''` or `"""`).

{{< highlight python >}}  
s1 = 'Hello'  
s2 = "World"  
s3 = '''This is a multi-line string'''  
print(s1, s2)  
{{< /highlight >}}

### Common Operations on Strings


| Operation     | Example                   | Description              |
| ------------- | ------------------------- | ------------------------ |
| Concatenation | `'Hello' + ' ' + 'World'` | Returns `'Hello World'`. |
| Repetition    | `'Hi' * 3`                | Returns `'HiHiHi'`.      |
| Indexing      | `'Hello'[0]`              | Returns `'H'`.           |
| Slicing       | `'Hello'[1:4]`            | Returns `'ell'`.         |
| Length        | `len('Hello')`            | Returns `5`.             |
| Membership    | `'e' in 'Hello'`          | Returns `True`.          |


### Common String Methods


| Method              | Example                     | Description                              |
| ------------------- | --------------------------- | ---------------------------------------- |
| `capitalize()`      | `'hello'.capitalize()`      | Returns `'Hello'`.                       |
| `lower()`           | `'HELLO'.lower()`           | Returns `'hello'`.                       |
| `upper()`           | `'hello'.upper()`           | Returns `'HELLO'`.                       |
| `strip()`           | `' hello '.strip()`         | Returns `'hello'` (removes whitespace).  |
| `replace(old, new)` | `'hello'.replace('l', 'L')` | Returns `'heLLo'`.                       |
| `split(delimiter)`  | `'a,b,c'.split(',')`        | Returns `['a', 'b', 'c']`.               |
| `join(iterable)`    | `'-'.join(['a', 'b'])`      | Returns `'a-b'`.                         |
| `find(sub)`         | `'hello'.find('e')`         | Returns `1` (index of first occurrence). |


---

## Type Conversion

Python allows you to convert between types using functions like `int()`, `float()`, `str()`, and `bool()`.

### Examples of Type Conversion

{{< highlight python >}}

# Integer to Float

x = int(5)  
y = float(x)  
print(y)  # Output: 5.0

# Float to Integer

z = float(3.9)  
w = int(z)  
print(w)  # Output: 3

# Number to String

num = 10  
num_str = str(num)  
print(num_str)  # Output: '10'

# String to Number

str_num = "123"  
integer_num = int(str_num)  
print(integer_num)  # Output: 123

# Boolean Conversion

print(bool(1))    # Output: True  
print(bool(0))    # Output: False  
print(bool(""))   # Output: False  
print(bool("Hello"))  # Output: True  
{{< /highlight >}}

---

## Checking Variable Types

You can check the type of a variable using the `type()` function or the `isinstance()` function.

{{< highlight python >}}  
x = 10  
print(type(x))  # Output: <class 'int'>

# Check if x is an integer

print(isinstance(x, int))  # Output: True

# Check if x is a float or integer

print(isinstance(x, (float, int)))  # Output: True  
{{< /highlight >}}

---

## Conclusion

Understanding Python’s **data types**—**integers, floats, complex numbers, booleans, and strings**—is fundamental to writing effective code. Each type has its own **operations and methods**, and Python’s dynamic typing allows for flexible and readable code.

---

{{< pageview >}}
