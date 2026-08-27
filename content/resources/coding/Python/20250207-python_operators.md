---
title: 'Operators'
date: '2026-02-07'
draft: false
categories: ["Coding", "Python"]
category_weight: 30
weight: 30
---

## Introduction

Operators are the **building blocks** of programming logic in Python. They allow you to perform **mathematical, comparison, logical, and other operations** on data. This guide covers Python’s built-in operators, which are essential for writing **complex and efficient code**.

---

## Arithmetic Operators

Arithmetic operators are used to perform **mathematical operations** like addition, subtraction, multiplication, and division.

### Basic Arithmetic Operators


| Operator | Name           | Example  | Result                                       |
| -------- | -------------- | -------- | -------------------------------------------- |
| `+`      | Addition       | `a + b`  | Sum of `a` and `b`                           |
| `-`      | Subtraction    | `a - b`  | Difference between `a` and `b`               |
| `*`      | Multiplication | `a * b`  | Product of `a` and `b`                       |
| `/`      | Division       | `a / b`  | Quotient of `a` and `b` (returns a float)    |
| `//`     | Floor Division | `a // b` | Quotient of `a` and `b` (returns an integer) |
| `%`      | Modulus        | `a % b`  | Remainder of `a` divided by `b`              |
| `**`     | Exponentiation | `a ** b` | `a` raised to the power of `b`               |


### Examples

{{< highlight python >}}  
a = 3  
b = 5

print(a + b)  # Output: 8  
print(a * b)  # Output: 15  
print(a - b)  # Output: -2  
print(a / b)  # Output: 0.6  
print(a // b) # Output: 0 (floor division)  
print(a % b)  # Output: 3 (modulus)  
print(a ** b) # Output: 243 (exponentiation)  
{{< /highlight >}}

---

## Comparison Operators

Comparison operators are used to **compare values** and return a **boolean** (`True` or `False`).


| Operator | Name                     | Example  | Result                                        |
| -------- | ------------------------ | -------- | --------------------------------------------- |
| `==`     | Equal                    | `a == b` | `True` if `a` equals `b`                      |
| `!=`     | Not equal                | `a != b` | `True` if `a` does not equal `b`              |
| `>`      | Greater than             | `a > b`  | `True` if `a` is greater than `b`             |
| `<`      | Less than                | `a < b`  | `True` if `a` is less than `b`                |
| `>=`     | Greater than or equal to | `a >= b` | `True` if `a` is greater than or equal to `b` |
| `<=`     | Less than or equal to    | `a <= b` | `True` if `a` is less than or equal to `b`    |


### Example

{{< highlight python >}}  
a = 3  
b = 5

print(a == b)  # Output: False  
print(a != b)  # Output: True  
print(a < b)   # Output: True  
print(a >= b)  # Output: False  
{{< /highlight >}}

---

## Logical Operators

Logical operators are used to **combine boolean values** and return a boolean result.


| Operator | Name | Example   | Result                                         |
| -------- | ---- | --------- | ---------------------------------------------- |
| `and`    | AND  | `a and b` | `True` if both `a` and `b` are `True`          |
| `or`     | OR   | `a or b`  | `True` if at least one of `a` or `b` is `True` |
| `not`    | NOT  | `not a`   | `True` if `a` is `False`                       |


### Example

{{< highlight python >}}  
a = True  
b = False

print(a and b)  # Output: False  
print(a or b)   # Output: True  
print(not a)    # Output: False  
{{< /highlight >}}

---

## Identity Operators

Identity operators are used to **compare the memory addresses** of two objects.


| Operator | Name         | Example      | Result                                        |
| -------- | ------------ | ------------ | --------------------------------------------- |
| `is`     | Identity     | `a is b`     | `True` if `a` and `b` are the same object     |
| `is not` | Not identity | `a is not b` | `True` if `a` and `b` are not the same object |


### Example

{{< highlight python >}}  
a = [1, 2, 3]  
b = a  
c = [1, 2, 3]

print(a is b)      # Output: True (same object)  
print(a is c)      # Output: False (different objects)  
print(a is not c)  # Output: True  
{{< /highlight >}}

---

## Membership Operators

Membership operators are used to **check if a value is present in a sequence** (e.g., list, tuple, string, set, dictionary).


| Operator | Name   | Example             | Result                             |
| -------- | ------ | ------------------- | ---------------------------------- |
| `in`     | In     | `x in sequence`     | `True` if `x` is in `sequence`     |
| `not in` | Not in | `x not in sequence` | `True` if `x` is not in `sequence` |


### Example

{{< highlight python >}}  
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)        # Output: True  
print("pineapple" not in fruits) # Output: True  
{{< /highlight >}}

---

## Bitwise Operators

Bitwise operators are used to **perform operations on binary numbers** (bits).


| Operator | Name             | Example  | Result                                  |
| -------- | ---------------- | -------- | --------------------------------------- |
| `&`      | AND              | `a & b`  | AND operation on each bit               |
| `        | `                | OR       | `a                                      |
| `^`      | XOR              | `a ^ b`  | XOR operation on each bit               |
| `~`      | NOT (Complement) | `~a`     | Inverts all bits of `a`                 |
| `<<`     | Left Shift       | `a << 2` | Shifts bits of `a` left by 2 positions  |
| `>>`     | Right Shift      | `a >> 2` | Shifts bits of `a` right by 2 positions |


### Example

{{< highlight python >}}  
a = 5    # Binary: 0101  
b = 3    # Binary: 0011

print(a & b)  # Output: 1 (Binary: 0001)  
print(a | b)  # Output: 7 (Binary: 0111)  
print(a ^ b)  # Output: 6 (Binary: 0110)  
print(~a)     # Output: -6 (Inverts all bits)  
print(a << 1) # Output: 10 (Binary: 1010)  
print(a >> 1) # Output: 2 (Binary: 0010)  
{{< /highlight >}}

---

## Assignment Operators

Assignment operators are used to **assign values to variables**.


| Operator | Example   | Equivalent To | Description                                                         |
| -------- | --------- | ------------- | ------------------------------------------------------------------- |
| `=`      | `a = 5`   | -             | Assigns `5` to `a`                                                  |
| `+=`     | `a += 3`  | `a = a + 3`   | Adds `3` to `a` and assigns the result to `a`                       |
| `-=`     | `a -= 3`  | `a = a - 3`   | Subtracts `3` from `a` and assigns the result to `a`                |
| `*=`     | `a *= 3`  | `a = a * 3`   | Multiplies `a` by `3` and assigns the result to `a`                 |
| `/=`     | `a /= 3`  | `a = a / 3`   | Divides `a` by `3` and assigns the result to `a`                    |
| `//=`    | `a //= 3` | `a = a // 3`  | Performs floor division of `a` by `3` and assigns the result to `a` |
| `%=`     | `a %= 3`  | `a = a % 3`   | Assigns the remainder of `a` divided by `3` to `a`                  |
| `**=`    | `a **= 3` | `a = a ** 3`  | Raises `a` to the power of `3` and assigns the result to `a`        |


### Example

{{< highlight python >}}  
a = 5

a += 3  # a = 8  
print(a)

a -= 2  # a = 6  
print(a)

a *= 4  # a = 24  
print(a)

a //= 5 # a = 4  
print(a)  
{{< /highlight >}}

---

## Operator Precedence

Operator precedence determines the **order in which operations are performed**. Operators with higher precedence are evaluated first.

Here is the **precedence order** (from highest to lowest):

1. Parentheses `()`
2. Exponentiation `**`
3. Unary operators (`+x`, `-x`, `~x`)
4. Multiplication, Division, Floor Division, Modulus (`*`, `/`, `//`, `%`)
5. Addition, Subtraction (`+`, `-`)
6. Bitwise Shift (`<<`, `>>`)
7. Bitwise AND (`&`)
8. Bitwise XOR (`^`)
9. Bitwise OR (`|`)
10. Comparison operators (`==`, `!=`, `>`, `<`, `>=`, `<=`)
11. Identity operators (`is`, `is not`)
12. Membership operators (`in`, `not in`)
13. Logical NOT (`not`)
14. Logical AND (`and`)
15. Logical OR (`or`)

### Example

{{< highlight python >}}

# Parentheses have the highest precedence

result = (5 + 3) * 2  
print(result)  # Output: 16

# Exponentiation has higher precedence than multiplication

result = 2 ** 3 * 2  
print(result)  # Output: 16 (2^3 = 8, 8 * 2 = 16)

# Multiplication has higher precedence than addition

result = 5 + 3 * 2  
print(result)  # Output: 11 (3 * 2 = 6, 5 + 6 = 11)  
{{< /highlight >}}

---

## Operations on Lists

Operators like `+` and `*` can be used with **lists** to perform concatenation and repetition.

### Example

{{< highlight python >}}  
a = [5, 3, 2, 8]  
b = [6, 9, 2, 3]

print(a + b)  # Output: [5, 3, 2, 8, 6, 9, 2, 3] (concatenation)  
print(4 * a)  # Output: [5, 3, 2, 8, 5, 3, 2, 8, 5, 3, 2, 8, 5, 3, 2, 8] (repetition)  
{{< /highlight >}}

---

## Operations on Strings

Operators like `+` and `*` can also be used with **strings** to perform concatenation and repetition.

### Example

{{< highlight python >}}  
a = "hello"  
b = "World"

print(a + " " + b)  # Output: "hello World" (concatenation)  
print(4 * a)        # Output: "hellohellohellohello" (repetition)  
{{< /highlight >}}

### Important Note

Operations must be performed between **compatible data types**. For example:

- You **cannot** add a boolean to a float directly.
- You **can** add an integer to a float (Python will convert the integer to a float).

---

## String Formatting

Python provides multiple ways to **format strings**, including **f-strings**, **raw strings (r-strings)**, and **format specifiers**.

### F-Strings (Formatted String Literals)

F-strings allow you to **embed expressions** directly inside string literals using curly braces `{}`.

{{< highlight python >}}  
name = "John"  
age = 23  
print(f"{name} is {age} years old.")  # Output: John is 23 years old.  
{{< /highlight >}}

### Raw Strings (r-strings)

Raw strings treat backslashes (`\`) as **literal characters** and do not process escape sequences.

{{< highlight python >}}  
print("C:\new\test")   # Output: C:\new\test (escape sequences processed)  
print(r"C:\new\test")  # Output: C:\new\test (literal backslashes)  
{{< /highlight >}}

### Format Specifiers (Old Style)

You can use **format specifiers** to format strings with placeholders.


| Specifier | Description                                         |
| --------- | --------------------------------------------------- |
| `%s`      | String (or any object with a string representation) |
| `%d`      | Integer                                             |
| `%f`      | Floating-point number                               |
| `%.2f`    | Floating-point number with 2 decimal places         |
| `%x`      | Integer in hexadecimal (lowercase)                  |
| `%X`      | Integer in hexadecimal (uppercase)                  |


#### Example

{{< highlight python >}}  
name = "John"  
age = 23  
print("%s is %d years old." % (name, age))  # Output: John is 23 years old.

# Floating-point formatting

pi = 3.14159  
print("Pi is approximately %.2f" % pi)  # Output: Pi is approximately 3.14

# Hexadecimal formatting

num = 255  
print("Hexadecimal: %x" % num)  # Output: Hexadecimal: ff  
{{< /highlight >}}

---

## Conclusion

Python’s **operators** are powerful tools for performing a wide range of operations on data. Understanding **arithmetic, comparison, logical, identity, membership, bitwise, and assignment operators**—as well as their precedence—is essential for writing **efficient and bug-free code**.

---

{{< pageview >}}
