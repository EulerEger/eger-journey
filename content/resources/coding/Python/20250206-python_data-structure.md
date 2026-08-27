---
title: 'Data structure'
date: '2026-02-06'
draft: false
categories: ["Coding", "Python"]
category_weight: 20
weight: 20
---

## Introduction

The dynamic part of programming begins here. Python provides built-in **data structures** to organize data types based on specific needs, allowing the creation of more complex structures. Data structures can be classified as **mutable or immutable**, **ordered or unordered**, and those that accept **duplicate elements**.

---

## Data Structures in Python

Depending on the situation, Python offers structures that allow efficient data access. For programs, accessing data can be compared to searching for a book in a library: without an organized system, you would have to check every book to find the one you need. In programming, this "library" is the computer's memory.

Python includes several built-in data structures, which can be classified as **mutable** or **immutable**.

Let’s explore them in detail.

---

## Lists

**Lists** are non-homogeneous dynamic arrays, meaning they can store different data types. They are **mutable** (you can add, remove, or update elements) and **ordered**. Like vectors in C++, list elements are stored contiguously in memory for fast access.

### Defining a List

A list can be defined in two ways:

- Using the `list()` function.
- Writing elements between square brackets, separated by commas.

{{< highlight python >}}  
my_list = [1, "hello", 3.14, True]  
empty_list = list()  
{{< /highlight >}}

### Common Operations on Lists


| Operation       | Example              | Description                                                           |
| --------------- | -------------------- | --------------------------------------------------------------------- |
| Access element  | `my_list[0]`         | Returns the first element (1).                                        |
| Slice           | `my_list[1:3]`       | Returns a sublist: `["hello", 3.14]`.                                 |
| Concatenation   | `my_list + [5, 6]`   | Combines two lists.                                                   |
| Repetition      | `my_list * 2`        | Repeats the list: `[1, "hello", 3.14, True, 1, "hello", 3.14, True]`. |
| Membership test | `"hello" in my_list` | Returns `True` if "hello" is in the list.                             |
| Length          | `len(my_list)`       | Returns the number of elements (4).                                   |


### Common List Methods


| Method             | Example                      | Description                                             |
| ------------------ | ---------------------------- | ------------------------------------------------------- |
| `append(x)`        | `my_list.append(5)`          | Adds `x` to the end of the list.                        |
| `extend(iterable)` | `my_list.extend([5, 6])`     | Adds all elements of the iterable to the end.           |
| `insert(i, x)`     | `my_list.insert(1, "world")` | Inserts `x` at index `i`.                               |
| `remove(x)`        | `my_list.remove("hello")`    | Removes the **first** occurrence of `x`.                |
| `pop([i])`         | `my_list.pop()`              | Removes and returns the last element (or at index `i`). |
| `clear()`          | `my_list.clear()`            | Removes all elements from the list.                     |
| `index(x)`         | `my_list.index("hello")`     | Returns the index of the first occurrence of `x`.       |
| `count(x)`         | `my_list.count(1)`           | Returns the number of times `x` appears.                |
| `sort()`           | `my_list.sort()`             | Sorts the list in place.                                |
| `reverse()`        | `my_list.reverse()`          | Reverses the list in place.                             |
| `copy()`           | `new_list = my_list.copy()`  | Returns a shallow copy of the list.                     |


---

## Tuples

**Tuples** are **immutable** sequences, typically used to store collections of heterogeneous data. Once created, their elements cannot be modified, added, or removed. They are **ordered** and allow duplicate elements.

### Defining a Tuple

A tuple can be defined in two ways:

- Using the `tuple()` function.
- Writing elements between parentheses, separated by commas.

{{< highlight python >}}  
my_tuple = (1, "hello", 3.14, True)  
single_element_tuple = (42,)  # Note the comma for single-element tuples  
{{< /highlight >}}

### Common Operations on Tuples


| Operation       | Example               | Description                                |
| --------------- | --------------------- | ------------------------------------------ |
| Access element  | `my_tuple[0]`         | Returns the first element (1).             |
| Slice           | `my_tuple[1:3]`       | Returns a subtuple: `("hello", 3.14)`.     |
| Concatenation   | `my_tuple + (5, 6)`   | Combines two tuples.                       |
| Repetition      | `my_tuple * 2`        | Repeats the tuple.                         |
| Membership test | `"hello" in my_tuple` | Returns `True` if "hello" is in the tuple. |
| Length          | `len(my_tuple)`       | Returns the number of elements (4).        |


### Note

Tuples do not have methods that modify their content (e.g., no `append`, `remove`, etc.), but they support methods like `count` and `index`:


| Method     | Example                   | Description                                       |
| ---------- | ------------------------- | ------------------------------------------------- |
| `count(x)` | `my_tuple.count(1)`       | Returns the number of times `x` appears.          |
| `index(x)` | `my_tuple.index("hello")` | Returns the index of the first occurrence of `x`. |


---

## Sets

**Sets** are unordered collections of **unique** elements. They are **mutable** and support mathematical set operations like union, intersection, and difference.

### Defining a Set

A set can be defined in two ways:

- Using the `set()` function.
- Writing elements between curly braces, separated by commas.

{{< highlight python >}}  
my_set = {1, 2, 3, 3, 4}  # Duplicates are automatically removed  
empty_set = set()  
{{< /highlight >}}

### Common Operations on Sets


| Operation            | Example           | Description                                                       |
| -------------------- | ----------------- | ----------------------------------------------------------------- |
| Union                | `my_set           | {4, 5}`                                                           |
| Intersection         | `my_set & {2, 3}` | Returns a new set with common elements.                           |
| Difference           | `my_set - {1, 2}` | Returns a new set with elements in `my_set` but not in the other. |
| Symmetric difference | `my_set ^ {2, 5}` | Returns a new set with elements in either set, but not both.      |
| Membership test      | `2 in my_set`     | Returns `True` if 2 is in the set.                                |
| Length               | `len(my_set)`     | Returns the number of elements (3).                               |


### Common Set Methods


| Method             | Example                   | Description                                                         |
| ------------------ | ------------------------- | ------------------------------------------------------------------- |
| `add(x)`           | `my_set.add(5)`           | Adds `x` to the set.                                                |
| `remove(x)`        | `my_set.remove(1)`        | Removes `x` from the set (raises `KeyError` if `x` is not present). |
| `discard(x)`       | `my_set.discard(1)`       | Removes `x` from the set (no error if `x` is not present).          |
| `pop()`            | `my_set.pop()`            | Removes and returns an arbitrary element.                           |
| `clear()`          | `my_set.clear()`          | Removes all elements from the set.                                  |
| `copy()`           | `new_set = my_set.copy()` | Returns a shallow copy of the set.                                  |
| `update(iterable)` | `my_set.update([4, 5])`   | Adds all elements from the iterable to the set.                     |


---

## Dictionaries

**Dictionaries** are mutable, unordered collections of **key-value pairs**. They are highly optimized for retrieving data based on a key. Keys must be **immutable** (e.g., strings, numbers, tuples).

### Defining a Dictionary

A dictionary can be defined using curly braces, with keys and values separated by colons.

{{< highlight python >}}  
my_dict = {"name": "Alice", "age": 25, "city": "Paris"}  
empty_dict = dict()  
{{< /highlight >}}

### Common Operations on Dictionaries


| Operation             | Example                          | Description                                                          |
| --------------------- | -------------------------------- | -------------------------------------------------------------------- |
| Access value          | `my_dict["name"]`                | Returns the value associated with the key "name".                    |
| Add/Update key-value  | `my_dict["age"] = 26`            | Adds or updates the key "age" with value 26.                         |
| Delete key            | `del my_dict["city"]`            | Removes the key "city" from the dictionary.                          |
| Membership test (key) | `"name" in my_dict`              | Returns `True` if "name" is a key in the dictionary.                 |
| Length                | `len(my_dict)`                   | Returns the number of key-value pairs (3).                           |
| Get value (safe)      | `my_dict.get("name", "Default")` | Returns the value for "name" or "Default" if the key does not exist. |
| Keys/Values/Items     | `my_dict.keys()`                 | Returns a view of keys/values/items.                                 |


### Common Dictionary Methods


| Method                     | Example                                   | Description                                                                      |
| -------------------------- | ----------------------------------------- | -------------------------------------------------------------------------------- |
| `clear()`                  | `my_dict.clear()`                         | Removes all key-value pairs from the dictionary.                                 |
| `copy()`                   | `new_dict = my_dict.copy()`               | Returns a shallow copy of the dictionary.                                        |
| `pop(key, [default])`      | `my_dict.pop("age")`                      | Removes and returns the value for `key`.                                         |
| `popitem()`                | `my_dict.popitem()`                       | Removes and returns an arbitrary key-value pair.                                 |
| `update(dict2)`            | `my_dict.update({"age": 26})`             | Updates the dictionary with key-value pairs from `dict2`.                        |
| `setdefault(key, default)` | `my_dict.setdefault("country", "France")` | Returns the value for `key`; if `key` does not exist, inserts it with `default`. |


---

## Conclusion

Python’s built-in data structures—**lists, tuples, sets, and dictionaries**—provide powerful tools for organizing and manipulating data efficiently. Understanding their properties (mutability, order, uniqueness) and methods is key to writing effective Python code.

---


