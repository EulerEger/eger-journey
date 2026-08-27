---
title: 'Functions'
date: '2026-02-09'
draft: false
categories: ["Coding", "Python"]
category_weight: 50
weight: 50
---

## Introduction

**Functions** are a convenient way to **organize your code** into reusable and modular blocks. They improve **readability**, **reusability**, and **efficiency** by allowing you to:

- Divide complex tasks into smaller, manageable parts.
- Avoid repeating the same code.
- Define clear interfaces for sharing code with others.

---

## Defining Functions

In Python, you define a function using the `def` keyword, followed by:

1. The **function name**.
2. **Parentheses** `()` containing optional **parameters**.
3. A **colon** `:`.
4. An **indented block** of code to execute.

### Syntax

```python
def function_name(parameter1, parameter2, ...):
    # Code to execute
    return result  # Optional
```

### Example: Simple Function

**Print numbers from `start` to `stop-1` with a given `step`:**  
{{< highlight python >}}  
def counter(start, stop, step):  
    i = start  
    while i < stop:  
        print(i)  
        i += step

counter(1, 7, 2)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
1  
3  
5  
{{< /highlight >}}

---

## Return Values

The `return` statement is used to **send a value back** to the caller of the function. If no `return` statement is used, the function returns `None` by default.

### Example: Function with Return

**Calculate the volume of a sphere:**  
{{< highlight python >}}  
import math

def sphere_volume(radius):  
    volume = (4 / 3) * math.pi * (radius ** 3)  
    return volume

volume = sphere_volume(3)  
print(f"The sphere volume is {volume:.2f} cubic meters")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
The sphere volume is 113.10 cubic meters  
{{< /highlight >}}

---

## Function Parameters

Parameters allow you to **pass data** into a function. They are defined inside the parentheses when declaring the function.

### Types of Parameters

1. **Positional Parameters**: Order matters.
2. **Keyword Parameters**: Specified by name.
3. **Default Parameters**: Assigned a default value if not provided.
4. **Variable-Length Parameters**: Use `*args` for arbitrary positional arguments and `**kwargs` for arbitrary keyword arguments.

### Example: Default Parameters

{{< highlight python >}}  
def greet(name, greeting="Hello"):  
    print(f"{greeting}, {name}!")

greet("Alice")  # Uses default greeting  
 greet("Bob", "Hi")  # Overrides default greeting  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
Hello, Alice!  
Hi, Bob!  
{{< /highlight >}}

### Example: Variable-Length Parameters

{{< highlight python >}}  
def sum_all(*args):  
    return sum(args)

def print_info(**kwargs):  
    for key, value in kwargs.items():  
        print(f"{key}: {value}")

print(sum_all(1, 2, 3))  # Output: 6  
print_info(name="Alice", age=25, city="Paris")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
6  
name: Alice  
age: 25  
city: Paris  
{{< /highlight >}}

---

## Variable Scope

Variables in Python have **scope**, which determines where they can be accessed.

### Local Variables

- Defined **inside a function**.
- Only accessible **within that function**.

### Global Variables

- Defined **outside any function**.
- Accessible **anywhere in the code**.

### The `global` Keyword

To modify a global variable inside a function, use the `global` keyword.

#### Example: Local vs. Global Variables

{{< highlight python >}}  
a = 2  
b = 7

def test():  
    b = 5  # Local variable  
    print(a, b)  # Accesses global 'a' and local 'b'

test()  
print(a, b)  # Accesses global 'a' and 'b'  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
2 5  
2 7  
{{< /highlight >}}

#### Example: Modifying Global Variables

{{< highlight python >}}  
count = 0

def increment():  
    global count  
    count += 1

increment()  
print(count)  # Output: 1  
{{< /highlight >}}

---

## Lambda Functions

**Lambda functions** are small, anonymous functions defined using the `lambda` keyword. They can have any number of arguments but only one expression.

### Syntax

```python
lambda arguments: expression
```

### Example: Lambda Function

**Square a number:**  
{{< highlight python >}}  
square = lambda x: x ** 2  
print(square(5))  # Output: 25  
{{< /highlight >}}

---

## Comprehensions

Comprehensions provide a **concise way** to create sequences (lists, sets, dictionaries) in Python.

### List Comprehension

**Syntax:**

```python
[expression for item in iterable (if condition)]
```

#### Example: List Comprehension

**Create a list of squares for numbers from 1 to 5:**  
{{< highlight python >}}  
squares = [n ** 2 for n in range(1, 6)]  
print(squares)  # Output: [1, 4, 9, 16, 25]  
{{< /highlight >}}

**With condition:**  
{{< highlight python >}}  
even_squares = [n ** 2 for n in range(1, 11) if n % 2 == 0]  
print(even_squares)  # Output: [4, 16, 36, 64, 100]  
{{< /highlight >}}

---

### Set Comprehension

**Syntax:**

```python
{expression for item in iterable (if condition)}
```

#### Example: Set Comprehension

**Create a set of squares for numbers from 1 to 5:**  
{{< highlight python >}}  
squares = {n ** 2 for n in range(1, 6)}  
print(squares)  # Output: {1, 4, 9, 16, 25}  
{{< /highlight >}}

**With condition:**  
{{< highlight python >}}  
even_squares = {n ** 2 for n in range(1, 11) if n % 2 == 0}  
print(even_squares)  # Output: {4, 16, 36, 64, 100}  
{{< /highlight >}}

---

### Dictionary Comprehension

**Syntax:**

```python
{key: value for item in iterable (if condition)}
```

#### Example: Dictionary Comprehension

**Create a dictionary of numbers and their squares:**  
{{< highlight python >}}  
squares = {n: n ** 2 for n in range(1, 6)}  
print(squares)  # Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}  
{{< /highlight >}}

**With condition:**  
{{< highlight python >}}  
even_squares = {n: n ** 2 for n in range(1, 11) if n % 2 == 0}  
print(even_squares)  # Output: {2: 4, 4: 16, 6: 36, 8: 64, 10: 100}  
{{< /highlight >}}

---

### Comprehension with `if-else`

You can use `if-else` logic within comprehensions.

#### Example: List Comprehension with `if-else`

**Replace the word "the" with 0 in a list of word lengths:**  
{{< highlight python >}}  
sentence = "the quick brown fox jumps over the lazy dog"  
words = sentence.split()  
word_lengths = [len(word) if word != "the" else 0 for word in words]  
print(word_lengths)  # Output: [0, 5, 5, 3, 5, 4, 0, 4, 3]  
{{< /highlight >}}

#### Example: Dictionary Comprehension with `if-else`

**Create a dictionary with word lengths, replacing "the" with 0:**  
{{< highlight python >}}  
word_lengths_dict = {word: len(word) if word != "the" else 0 for word in words}  
print(word_lengths_dict)  
{{&nbsp;}}  
{{< /highlight >}}
**Output:**  
{{< highlight text >}}  
{'the': 0, 'quick': 5, 'brown': 5, 'fox': 3, 'jumps': 5, 'over': 4, 'lazy': 4, 'dog': 3}  
{{< /highlight >}}

---

## Nested Functions

You can define a function **inside another function**. The nested function is only accessible within the outer function.

### Example: Nested Function

{{< highlight python >}}  
def outer_function(text):  
    def inner_function():  
        return text.upper()  
    return inner_function()

print(outer_function("hello"))  # Output: HELLO  
{{< /highlight >}}

---

## Recursive Functions

A **recursive function** is a function that calls itself. It must have a **base case** to stop the recursion.

### Example: Factorial with Recursion

{{< highlight python >}}  
def factorial(n):  
    if n == 0:  
        return 1  
    else:  
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120  
{{< /highlight >}}

---

## Docstrings

**Docstrings** are used to document functions. They are enclosed in triple quotes (`"""` or `'''`).

### Example: Function with Docstring

{{< highlight python >}}  
def add(a, b):  
    """  
    Add two numbers and return the result.

```
Parameters:
a (int/float): First number
b (int/float): Second number

Returns:
int/float: Sum of a and b
"""
return a + b
```

print(add(3, 5))  # Output: 8  
{{< /highlight >}}

---

## Conclusion

Functions are a **powerful tool** in Python for organizing, reusing, and sharing code. Key takeaways:

- Use `def` to define functions.
- Use `return` to send back results.
- Understand **variable scope** (local vs. global).
- Use **lambda functions** for small, anonymous tasks.
- Use **comprehensions** for concise sequence creation.
- Document your functions with **docstrings**.

---

{{< pageview >}}
