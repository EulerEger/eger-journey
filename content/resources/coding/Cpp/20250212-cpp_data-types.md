---
title: 'Data types'
date: '2026-02-12'
draft: false
categories: ["Coding", "Cpp"]
category_weight: 10
weight: 10
---

## Introduction

C++ or Cpp is a programming language derived from c that is also considered as a middle-level programming language, due to the capability of handling hardware level and its human like readability. This makes it heavily powerful tool or a risky nightmare if the code is miss set.

## Variables and Types

Cpp is a statically typed programming language, which means that the variables must be declared before being compiled. Cpp present the fallowing data types:

|Data Type |Size in Bytes(bits)  |Meaning              |Range            |
|----------|---------------------|---------------------|-----------------|
|`int`     |     4 (32)          |Integer              | ± 2 147 483 647 |
|`float`   |     4 (32)          |Floating point       | ± 3.4 × 10^38   |
|`double`  |     8 (64)          |Double Floating point| ± 1.7 × 10^308  |
|`char`	  |     1 (8)           |Character	          | ± 256           |
|`wchar_t` |     2 (16)          |Wide Character       | ± 65 536        |
|`bool`	  |     1 (8)           |Boolean	             | 0 & 1           |
|`void`	  |     0 (0)           |Empty	             | 0               |

## Numbers :
There are two types of numeric variables: integer (whole numbers) and floating point (decimals). The syntax for those is ease to show.

### Integers

**Integers** are represented by the keyword `int`. Its size is usually 4 bytes. Meaning, it can store values from -2147483648 to 2147483647.

{{<highlight cpp>}}
#include <iostream>
using namespace std;
 
int main () {
   // number definition:
   int a =1;
   int b = 2.5;
     
   // number printing;
   cout << "a :" << a << endl;
   cout << "b :" << b << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}
a :1 
b :2
{{< /highlight >}}
### Floats and Doubles
**Float** and **Double** are represented by the keywords `float` and `double`. The size of `float` is 4 bytes and the size of `double` is 8 bytes. Hence, `double` has two times the precision of `float`. 

{{< highlight cpp >}}
#include <iostream>
using namespace std;
 
int main () {
   // number definition:
   float a =1;
   float b = 2.5;
     
   // number printing;
   cout << "a :" << a << endl;
   cout << "b :" << b << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}
a :1.0 
b :2.5
{{< /highlight >}}

### Complex
For the **complex numbers**, the keyword `complex` accepts two parameters, the first is for the real part and the second one is for the imaginary part. In Cpp there is not a built-in functionality for handling complex math, a special library called complex is required  

{{< highlight cpp >}}
#include <iostream>
#include <complex>
using namespace std::complex_literals;
 
int main () {
   // number definition:
   complex<double> a (1,0);
   complex<double> b (2,5);
     
   // number printing;
   cout << "a :" << a << endl;
   cout << "b :" << b << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}
a :(1,0) 
b :(2,5)
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

## Characters
Cpp treats the letters and words differently, as single letter characters(`char`), and wide characters(`wchar_t`). In Cpp the principal difference in characters is that `char` is a byte and `wchar_t` is 2 bytes; it is used to represent characters that require more memory. 

{{< highlight cpp >}}
#include <iostream>

using namespace std;
 
int main () {
   // char and strings definition:
   char a = 'h';
    
   // number printing;
   cout << "a :" << a << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}
a :h
{{< /highlight >}}

 As mentioned before, Cpp is a heritage from C, both of them are statically typed, which means you can declare a variable without assigning a value. 

{{< highlight cpp >}}
#include <iostream>

using namespace std;
 
int main () {
   // variable definition:
   char x ;
   
   //Variable assignment
   x = 7;

   // number printing;
   cout << "x :" << x << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}
x :7
{{< /highlight >}}

## Boolean

The logic behind programming is the binary system, but is also interpreted as `true` for 1 and `false` for 0. This binary-logic system is called Booleans in Cpp they are assignend with the keyword `bool`.

{{< highlight cpp >}}
#include <iostream>

using namespace std;
 
int main () {
   // variable definition:
   bool cond, val ;
 
   
   //Variable assignment
   cond = true;
   val = false;
   // number printing;
   cout << "the condition is " << cond << ", but the value is " << val << endl;
   return 0;
}
{{< /highlight >}}
**output:**
{{< highlight text >}}

the condition is 1, but the value is 0

{{< /highlight >}}

## void

C and Cpp have a peculiar variable type called void, and its only utility is to represent the void more exactly the absences of data. We will see its practicality later on.

# Type modifiers
We can modify some of the fundamental data types by using type modifiers. There are 4 types modifiers in Cpp:

1.  `signed`
2.  `unsigned`
3.  `short`
4.  `long`

We can modify the following data types with the above modifiers:

`int`
`double`
`char`

This means that we can modify the memory usage of variables.


|Data Type           |Size in Bytes(bits) |Meaning                        |
|--------------------|-------------|--------------------------------------|
|`signed int`        |    4 (32)   |used for integers                     |
|`unsigned int`      |    4 (32)   |can not store non-negative integers   |
|`short`             |    2 (16)   |used for small integers               |
|`long`  	         |    4 (32)   |used for large integers               |
|`unsigned long`     |    8 (64)   |used for large positives integers or 0|
|`long long`   	   |    8 (64)   |used for very large integers          |
|`unsigned long long`|    8 (64)   |used for very large positives integers|
|`long double`       |    8 (64)   |used for large flouting point         |
|`signed char` 	   |    1 (8)    |used for characters                   |
|`unsigned char`     |    1 (8)    |used for characters                   |

`signed` and `unsined` are used to assign positive only values or not.

`long` is used to expand the size of a variable.
  



{{< pageview >}}