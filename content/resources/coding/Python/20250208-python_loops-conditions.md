---
title: 'Loops and Conditionals'
date: '2026-02-08'
draft: false
categories: ["Coding", "Python"]
category_weight: 40
weight: 40
---

## Introduction

Python is a **high-level programming language** widely used in science, engineering, and many other fields. It is **user-friendly** and allows users to interact with a computer using simple, readable syntax instead of complex assembly or binary commands.

This guide covers **loops** (`for` and `while`) and **conditionals** (`if`, `elif`, `else`), which are fundamental for controlling the flow of your programs.

---

## Loops

Loops allow you to **repeat a block of code** multiple times. Python provides two primary types of loops: `for` and `while`.

---

### For Loops

A `**for` loop** is used to **iterate over a sequence** (e.g., a list, tuple, string, or range). The `range()` function is commonly used to generate a sequence of numbers.

#### The `range()` Function

The `range()` function generates a sequence of numbers. It can take up to three arguments:

- `range(stop)`: Generates numbers from `0` to `stop-1`.
- `range(start, stop)`: Generates numbers from `start` to `stop-1`.
- `range(start, stop, step)`: Generates numbers from `start` to `stop-1`, incrementing by `step`.

#### Examples

**Print numbers from 0 to 4:**  
{{< highlight python >}}  
for x in range(5):  
    print(x)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
1  
2  
3  
4  
{{< /highlight >}}

**Print numbers from 3 to 5:**  
{{< highlight python >}}  
for x in range(3, 6):  
    print(x)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
3  
4  
5  
{{< /highlight >}}

**Print numbers from 3 to 7, stepping by 2:**  
{{< highlight python >}}  
for x in range(3, 8, 2):  
    print(x)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
3  
5  
7  
{{< /highlight >}}

#### Iterating Over Sequences

You can also iterate directly over sequences like lists, tuples, or strings.

{{< highlight python >}}  
fruits = ["apple", "banana", "cherry"]  
for fruit in fruits:  
    print(fruit)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
apple  
banana  
cherry  
{{< /highlight >}}

---

### While Loops

A `**while` loop** repeats a block of code **as long as a condition is `True**`. It is often used for **infinite loops** or loops where the number of iterations is not known in advance.

#### Example

**Print numbers from 0 to 4:**  
{{< highlight python >}}  
count = 0  
while count < 5:  
    print(count)  
    count += 1  # Increment count by 1  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
1  
2  
3  
4  
{{< /highlight >}}

#### Infinite Loop Example

A `while` loop with a condition that is always `True` will run indefinitely unless broken.

{{< highlight python >}}  
while True:  
    user_input = input("Enter 'quit' to exit: ")  
    if user_input == "quit":  
        break  
    print(f"You entered: {user_input}")  
{{< /highlight >}}

---

### Break and Continue

- `**break**`: Exits the loop immediately.
- `**continue**`: Skips the current iteration and moves to the next one.

#### Example with `break`

**Exit the loop when `count` reaches 5:**  
{{< highlight python >}}  
count = 0  
while True:  
    print(count)  
    count += 1  
    if count >= 5:  
        break  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
1  
2  
3  
4  
{{< /highlight >}}

#### Example with `continue`

**Skip even numbers:**  
{{< highlight python >}}  
for i in range(10):  
    if i % 2 == 0:  
        continue  
    print(i)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
1  
3  
5  
7  
9  
{{< /highlight >}}

---

### The `else` Clause in Loops

In Python, loops can have an `**else` clause** that executes **after the loop completes normally** (i.e., not terminated by a `break` statement).

#### Example with `for` and `else`

**Print a message after the loop completes:**  
{{< highlight python >}}  
for i in range(5):  
    print(i)  
else:  
    print("Loop completed successfully!")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
1  
2  
3  
4  
Loop completed successfully!  
{{< /highlight >}}

#### Example with `while` and `else`

**Print a message when `count` reaches 5:**  
{{< highlight python >}}  
count = 0  
while count < 5:  
    print(count)  
    count += 1  
else:  
    print(f"count value reached {count}")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
1  
2  
3  
4  
count value reached 5  
{{< /highlight >}}

#### Example with `break` and `else`

**The `else` block is skipped if the loop is terminated by `break`:**  
{{< highlight python >}}  
for i in range(1, 10):  
    if i % 5 == 0:  
        break  
    print(i)  
else:  
    print("This is not printed because the loop was terminated by 'break'.")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
1  
2  
3  
4  
{{< /highlight >}}

---

## Conditionals

Conditionals allow you to **execute different blocks of code based on whether a condition is `True` or `False**`. Python uses the keywords `if`, `elif` (short for "else if"), and `else` for conditionals.

---

### If, Elif, and Else

- `**if**`: Executes a block of code if a condition is `True`.
- `**elif**`: Checks another condition if the previous `if` or `elif` condition was `False`.
- `**else**`: Executes a block of code if all previous conditions were `False`.

#### Example

**Assign a grade based on a score:**  
{{< highlight python >}}  
score = 85

if score == 100:  
    grade = "A++"  
elif score >= 95:  
    grade = "A+"  
elif score >= 90:  
    grade = "A"  
elif score >= 80:  
    grade = "B"  
elif score >= 70:  
    grade = "C"  
elif score >= 60:  
    grade = "D"  
else:  
    grade = "F"

print("Your grade is:", grade)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
Your grade is: B  
{{< /highlight >}}

---

### Boolean Logic in Conditionals

You can use **boolean operators** (`and`, `or`, `not`) to build **complex conditions**.

#### Example

**Check if a number is between 10 and 20:**  
{{< highlight python >}}  
number = 15

if number >= 10 and number <= 20:  
    print(f"{number} is between 10 and 20.")  
else:  
    print(f"{number} is not between 10 and 20.")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
15 is between 10 and 20.  
{{< /highlight >}}

---

### The `in` Operator

The `in` operator checks if a value exists in a sequence (e.g., list, tuple, string, set, dictionary).

#### Example

**Check if a fruit is in a list:**  
{{< highlight python >}}  
fruits = ["apple", "banana", "cherry"]

if "banana" in fruits:  
    print("Banana is in the list!")  
else:  
    print("Banana is not in the list.")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
Banana is in the list!  
{{< /highlight >}}

---

### The `is` Operator

The `is` operator checks if two variables refer to the **same object** in memory, not just if their values are equal.

#### Example

**Compare two variables:**  
{{< highlight python >}}  
a = [1, 2, 3]  
b = a  
c = [1, 2, 3]

if a is b:  
    print("a and b refer to the same object.")  
else:  
    print("a and b do not refer to the same object.")

if a is c:  
    print("a and c refer to the same object.")  
else:  
    print("a and c do not refer to the same object.")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
a and b refer to the same object.  
a and c do not refer to the same object.  
{{< /highlight >}}

---

### Indentation in Python

Python uses **indentation** (whitespace at the beginning of a line) to define code blocks, instead of brackets or braces. The standard indentation is **4 spaces**, but you can use tabs or any consistent number of spaces.

#### Example

**Correct indentation:**  
{{< highlight python >}}  
if 5 > 2:  
    print("Five is greater than two!")  
    print("This is also part of the if block.")  
print("This is not part of the if block.")  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
Five is greater than two!  
This is also part of the if block.  
This is not part of the if block.  
{{< /highlight >}}

---

## Nested Loops and Conditionals

You can **nest loops and conditionals** to create more complex logic.

### Example

**Print even numbers from 0 to 9:**  
{{< highlight python >}}  
for i in range(10):  
    if i % 2 == 0:  
        print(i)  
{{< /highlight >}}  
**Output:**  
{{< highlight text >}}  
0  
2  
4  
6  
8  
{{< /highlight >}}

---

## Conclusion

**Loops** (`for` and `while`) and **conditionals** (`if`, `elif`, `else`) are essential for controlling the flow of your Python programs. They allow you to:

- Repeat actions with loops.
- Make decisions with conditionals.
- Combine them for complex logic.

Understanding these concepts is key to writing **efficient and readable Python code**.

---

{{< pageview >}}
