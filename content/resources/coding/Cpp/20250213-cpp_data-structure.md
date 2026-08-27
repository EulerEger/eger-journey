---
title: 'Data structure'
date: '2026-02-13'
draft: false
categories: ["Coding", "Cpp"]
category_weight: 20
weight: 20
---

# Data structures

Data structures are fundamental components used to organize, manage and store data. In C++, those are the built-in arrays, the standard template library (STL) and user-defined structures. Depending on the situation, you can use a particular STL adapted to the task in hand, or build your own.

## Arrays

In Cpp an array is a variable that can store multiple values of the same type by assigning a memory slot for those values. Arrays are statics assigned, which means that when they are created they will not allow more values inside, but they are mutable.

In order to declare an array you must declare the data type and declare the size of the array in brackets:

```Cpp
int x[6];
```

Here:
- data type is `int`
- variable is `x`
- size `6` 

There several ways to declare an array, and we are not forced to use the full size of an array, it can handle empty spaces if they are not assigned. In the case you assign variables to an array without declaring the size the system will handle it automatically.

### Array indexing

In C++, each element in an array is associated with a number. The number is known as an array index. We can access elements of an array by using those indices.

`array[index];`

{{<highlight Cpp>}}
#include <iostream>

using namespace std;

int main()
{
    // declare and initialize an array
    int x[6] = {19, 10, 8, 17, 9, 15};

    // alternative to declare an array
    int x1[] = {19, 10, 8, 17, 9, 15};
    int x2[6] = {19, 10, 8};
    
    //for printing the i'th element
    
    for(int i=0;i<5;i++)
    {
      cout<< x[i] << " ";
    }
    cout<< endl;
    for(int i=0;i<5;i++)
    {
      cout<< x1[i] <<" ";
    }
    cout<< endl;
    for(int i=0;i<5;i++)
    {
      cout<< x2[i] <<" ";
    }
    return 0;
}
{{</highlight>}}
**Output:**
{{<highlight text>}}
19 10 8 17 9 
19 10 8 17 9 
19 10 8 0 0 
{{</highlight>}}

### Multidimensional arrays

We can create arrays of an array, known as a multidimensional array. It is helpful for multidimensional functions and for linear algebra operations.

Like a normal array, we can initialize a multidimensional array in more than one way.

{{<highlight cpp>}}
int test[2][3] = {1, 2, 3, 4, 5, 6};
{{</highlight>}}

This method is not preferred. A better way to initialize this array with the same array elements is as follows:

{{<highlight cpp>}}
int test[2][3] = { {1, 2, 3}, {4, 5, 6}};
{{</highlight>}}

For a 3 dimension arrays it works in the same way and so on for n-dimension:

{{<highlight cpp>}}
int test[2][3][4] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 
                      1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};
{{</highlight>}}

Once again, This method is not preferred. A better way to initialize this three-dimension array with the same array elements is as follows:

{{<highlight cpp>}}
int test[2][3][4] = {
                  {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}},
                  {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}}
                  };
{{</highlight>}}

## Strings
There is not strings-structures natively in Cpp, the strings are char arrays. There are two types of strings commonly used in C++ : 

- C-strings (C-style Strings)
- Strings that are objects of string class (The Standard Library String Class)

### C-strings
In C the collection of characters is stored in the form of arrays terminated with a null character. 

### String class
In Cpp there is an object string that can hold strings. These strings are not fixed length objects and can be extended as needed.

{{<highlight Cpp>}}
#include <iostream>
#include<string>
using namespace std;

int main()
{
    // Declaring C-Strings
    char c_str1[12] = "C-string";
    // Alternatives
    char c_str2[] = {'C','-','s','t','r','i','n','g','\0'};
    char c_str3[12] = {'C','-','s','t','r','i','n','g','\0'};
 
    // Declaring a string object
    string cpp_str = "Cpp string";

    cout << c_str1;
    cout << c_str2 << endl;
    cout << c_str3 << endl;
    cout << cpp_str << endl;
    return 0;
}
{{</highlight>}}
**Output:**
{{<highlight text>}}
C-string
C-string
C-string
Cpp string
{{</highlight>}}

Like arrays, it is not necessary to use all the space allocated for the string.

An important difference between `char` and `string` is that for character single quotation marks ('') is used, and for strings is used double quotation marks (" ").

The common functions that are used with the string class are.

|Function	  |Description                                              |
|-----------|---------------------------------------------------------|
|`find()`	  |Find a substring in the string.                          |
|`rfind()`	|Find the last occurrence of a substring in the string.   |
|`append()`	|Append to the string.                                    |
|`insert()`	|Insert into the string.                                  |
|`erase()`	|Erase characters from the string.                        |
|`replace()`|Replace portions of the string.                          |
|`compare()`|Compare two strings.

## Standard Template Library (STL)

Cpp provides a set of programming tools to implement algorithms and data structure. These data structures and algorithms implement general-purpose classes and functions that have been tested rigorously, and this package take the name as Standard Template Library or STL in short.

STL has 3 major components:

- Containers
- Iterators: 
- Algorithms

### STL Containers

The containers are objects that store data and organize them in a specific manner as required.

The STL containers can be classified into 2 types:

1. Sequence:
- Array
- Vector
- Queue
- Deque
- List
- stack

2. Association:
- Set
- Map

#### Array

It is a container class that encapsulates fixed size arrays it is similar to the arrays as it stores multiples values of similar type.

**Declaration :**

``` cpp
#include <array>

// declaration of std::array 
std::array<T, N> array_name;
```
where,

`T` - Type of element to be stored
`N` - Number of elements in the array

The initialization of an array can be done in two ways:

**Method 1:**

```cpp
// initializer list
std::array<int, 5> numbers = {1, 2, 3, 4, 5};
```

**Method 2:**

```cpp
// initializer list
std::array<int, 5> numbers  {1, 2, 3, 4, 5};
```

Arrays are mutable and indexed, you can access to all values and modify them using the index.

{{<highlight cpp>}}

#include <iostream>
#include <array>

using namespace std;

int main(){
    array <int, 5> numbers {1, 2, 3, 4, 5};

    // accessing using the [] operator
    cout << "First element: " << numbers[0] << '\n';

    // accessing using the at method
    cout << "Second element: " << numbers.at(1) << '\n';

    // modify the element at index 0
    numbers[0] = 8;

    cout << "Modifying first element: " << numbers[0] << '\n';

    // modify the element at index 1
    numbers.at(1) = 90;

    cout << "Modifying second element: " << numbers[1] << '\n';
}
{{</highlight>}}
**Output:**
{{<highlight text>}}
First element: 1
Second element: 2
Modifying first element: 8
Modifying second element: 90
{{</highlight>}}

The common functions that are used with the string class are.

|Function	      |Description                        |
|---------------|-----------------------------------|
|`begin()`      |Return iterator to beginning.      |
|`end()`	      |Return iterator to beginning.      |
|`swap()`	      |Swap content.                      |
|`fill()`	      |Fill the array with value.         |
|`size()`   	  |Return size.                       |
|`max_size()`	  |Return size.                       |
|`empty()`      |Return max size.                   |

#### Vector

It is a container to store elements of similar types. However, unlike arrays, the size of a vector can grow dynamically. Which means that we can change the vector size during the execution of a program.

Vectors follows the same logic that arrays.

**Declaration :**

``` cpp
#include <array>

// declaration of std::array 
std::vector<T> vector_name;
```
where,

`T` - Type of element to be stored

The initialization of an array can be done in two ways:

**Method 1:**

```cpp
// initializer list
std::vector<int> vector1 = {1, 2, 3, 4, 5};
```

**Method 2:**

```cpp
// initializer list
std::vector<int> vector(5,1);
```

{{<highlight cpp>}}
#include <iostream>
#include <vector>
using namespace std;

int main() {

  // initializer list
  vector<int> vector = {1, 2, 3, 4, 5};
  //vector<int> vector {6, 7, 8, 9, 10};
  //vector<int> vector (5, 12);

  cout << "vector = ";

  // ranged loop
  for (const int& i : vector1) {
    cout << i << "  ";
  }

  // add the integers 6 and 7 to the vector

  vector.push_back(6);
  vector.push_back(7);

  cout << "\nUpdated Vector: ";

  for (const int& i : vector) {
    cout << i << "  ";
  }

  cout << "Element at Index 0: " << vector.at(0) << endl;
  cout << "Element at Index 2: " << vector[2] << endl;

  // change elements at indexes 1 and 4

  vector.at(1) = 9;
  vector[4] = 7;

  cout << "\nUpdated Vector: ";

  for (const int& i : vector) {
    cout << i << "  ";
  }

  // remove the last element
  vector.pop_back();

  // final vector
  cout << "\nUpdated Vector: ";
  for (int i : vecctor) {
    cout << i << " ";
  }

  return 0;
}
{{</highlight>}}

The vector header file provides various functions that can be used to perform different operations on a vector.

|Function	    |Description                                          |
|-------------|-----------------------------------------------------|
|`size()`	    |returns the number of elements present in the vector |
|`clear()`    |removes all the elements of the vector               |
|`front()`    |returns the first element of the vector              |
|`back()`	    |returns the last element of the vector               |
|`empty()`    |returns 1 (true) if the vector is empty              |
|`capacity()`	|check the overall size of a vector                   |


#### List, Queue, Deque, and Stacks

They are containers that store elements in random, unrelated locations. To maintain sequential order, each element contains two links: one that points to the previous element and one that points to the next one. The main difference is as shown:

- List are accessed by anywhere 
- Stacks (LIFO) are accessed by the tops (Firs-In, First-Out)
- Queue (FIFO) are accessed by the ends (First-In, First-Out)
- Deque by both ends (Double Ended Queue)

### Map and set

They are associated containers that hold data in an ordered manner, mainly arranged in ascending order of their keys values. For the maps is stored a pair of data known as key-value pair where each key is unique while the associated value does not have to be unique, meanwhile the sets store unique elements (keys) of the same type in a sorted manner.

