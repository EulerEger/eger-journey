---
title: 'Data Types in C++'
date: 2026-02-12
draft: false
categories: ["Coding", "Cpp"]
description: 'Explore the fundamental data types in C++, their sizes, ranges, and practical usage with examples.'
weight: 30
---

## Introduction
C++ is a **middle-level programming language** derived from C. It combines **low-level hardware control** with **high-level readability**, making it both powerful and flexible. However, improper use can lead to complex or risky code.

This article covers the **fundamental data types** in C++, their characteristics, and how to use them effectively.

---

## Variables and Types
C++ is a **statically typed language**, meaning **variable types must be declared before compilation**. Below is a table summarizing the primary data types in C++:

<mui:table-metadata title=\"C++ Data Types Overview\" />

| Data Type   | Size (Bytes/Bits) | Description            | Range                     |
|-------------|-------------------|------------------------|---------------------------|
| `int`       | 4 (32)            | Integer                | -2,147,483,648 to 2,147,483,647 |
| `float`     | 4 (32)            | Single-precision float | ±3.4 × 10^-38 to ±3.4 × 10^38 |
| `double`    | 8 (64)            | Double-precision float | ±1.7 × 10^-308 to ±1.7 × 10^308 |
| `char`      | 1 (8)             | Character              | -128 to 127 (or 0 to 255) |
| `wchar_t`   | 2 (16)            | Wide character         | 0 to 65,535               |
| `bool`      | 1 (8)             | Boolean                | `true` (1) or `false` (0) |
| `void`      | 0 (0)             | No type (empty)        | N/A                       |

---

## Numeric Types

### Integers
An integer is like a box that can only hold whole numbers. If you try to put a decimal in it, the decimal part will be discarded.
In C++, the "int" keyword is used to invoke an integer. It typically occupies 4 bytes and can store values from -2,147,483,648 to 2,147,483,647.

#### Example: Integer Usage
```cpp
#include <iostream>
using namespace std;

int main() {
    // Integer definition
    int a = 1;
    int b = 2;  // Note: Decimal part is truncated

    // Output
    cout << \"a: \" << a << endl;
    cout << \"b: \" << b << endl;
    return 0;
}
```
**Output:**
```
a: 1
b: 2
```

---

### Floating-Point Numbers
#### Floats and Doubles
A floating-point number represents decimal numbers. It is similar to a ruler marked in centimeters that has large and small markings to provide more greater precision in measurements. Here we can define two types: float (a ruler marked in centimeters), and double (a ruler marked in millimeter for greater precision).

- Float: 4 bytes, single-precision floating-point.
- Double: 8 bytes, double-precision floating-point.

#### Example: Float and Double Usage
```cpp
#include <iostream>
using namespace std;

int main() {
    // Float and double definition
    float a = 1.0f;  // 'f' suffix for float literal
    double b = 2.5;

    // Output
    cout << \"a: \" << a << endl;
    cout << \"b: \" << b << endl;
    return 0;
}
```
**Output:**
```
a: 1.0
b: 2.5
```

---
### Complex Numbers
C++ supports **complex numbers** via the `<complex>` library. The `complex` keyword takes **two parameters**: the real and imaginary parts.

#### Example: Complex Number Usage
```cpp
#include <iostream>
#include <complex>
using namespace std;

int main() {
    // Complex number definition
    complex<double> a(1.0, 0.0);  // Real: 1.0, Imaginary: 0.0
    complex<double> b(2.0, 5.0);  // Real: 2.0, Imaginary: 5.0

    // Output
    cout << \"a: \" << a << endl;
    cout << \"b: \" << b << endl;
    return 0;
}
```
**Output:**
```
a: (1,0)
b: (2,5)
```

---
## Characters and Booleans

### Characters (`char` and `wchar_t`)
- `char`: **1 byte**, stores a single character (ASCII).
- `wchar_t`: **2 bytes**, stores wide characters (Unicode).

#### Example: Character Usage
```cpp
#include <iostream>
using namespace std;

int main() {
    char letter = 'A';
    wchar_t wide_letter = L'B';  // 'L' prefix for wide character

    cout << \"Letter: \" << letter << endl;
    wcout << \"Wide letter: \" << wide_letter << endl;
    return 0;
}
```

---
### Booleans (`bool`)
- Represents **`true` (1)** or **`false` (0)**.

#### Example: Boolean Usage
```cpp
#include <iostream>
using namespace std;

int main() {
    bool is_valid = true;

    if (is_valid) {
        cout << \"Valid!\" << endl;
    }
    return 0;
}
```
**Output:**
```
Valid!
```

---
### 3. Type Modifiers

Type modifiers allow you to modify the size and behavior of basic data types.


| **Modifier** | **Description**                                                         | **Example**             |
| ------------ | ----------------------------------------------------------------------- | ----------------------- |
| `signed`     | Indicates that the variable can hold both positive and negative values. | `signed int x = -10;`   |
| `unsigned`   | Indicates that the variable can only hold positive values.              | `unsigned int y = 10;`  |
| `short`      | Reduces the size of the variable (typically 2 bytes for `int`).         | `short int z = 100;`    |
| `long`       | Increases the size of the variable (typically 8 bytes for `int`).       | `long int w = 1000000;` |


---
## Practical Considerations
- **Truncation**: Assigning a floating-point value to an `int` **truncates** the decimal part (e.g., `int b = 2.5;` → `b = 2`).
- **Precision**: Use `double` for higher precision calculations.
- **Portability**: Sizes of `int`, `float`, etc., can vary by system. Use `sizeof(type)` to check:
  ```cpp
  cout << \"Size of int: \" << sizeof(int) << \" bytes\" << endl;
  ```

---
## Common Pitfalls
1. **Overflow**: Exceeding the range of a data type (e.g., `int` beyond ±2 billion) causes **undefined behavior**.
2. **Implicit Conversion**: C++ may silently convert types (e.g., `float` to `int`), leading to data loss.
3. **Uninitialized Variables**: Always initialize variables to avoid garbage values.


---
## Conclusion
- C++ offers a **rich set of data types** for various use cases.
- **Static typing** ensures type safety but requires explicit declarations.
- Always consider **range, precision, and portability** when choosing a data type.


