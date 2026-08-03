---
tags:
  - topic/coding/cplusplus
  - status/wip
  - type/concept
  - type/commands
aliases:
date:
---
Taken from [link](https://www.geeksforgeeks.org/cpp/cpp-cheatsheet/)
## Basic Structure of C++ Program
```C++
// Header file for input and output
#include <iostream>

// To avoid using std:: before cout and cin
using namespace std;

// Main function - entry point of every C++ program
int main()
{
    // Display output on the screen
    cout << "Hello, World!" << endl;

    // Take input from the user
    int num;
    cout << "Enter a number: ";
    cin >> num;

    // Display the entered number
    cout << "You entered: " << num << endl;

    // Indicates successful program execution
    return 0;
}
```
Called this *examplecode.cpp*
## Comments
- [*Comments*](https://www.geeksforgeeks.org/cpp/cpp-comments/) are used for providing an explanation of the code that makes it easier for others to understand the functionality of the code. 
- They are not executed by the compiler. 
- Comments can also be used to temporarily disable specific statements of code without deleting them.
	### There are two types of comments
	1. **Single-line**: starts with `//`
	2. **Multi-line:** starts with `/*` and ends with `*/`
## Variables
- A variable is a container used to store data values and must be declared before they can be used. 
- You can declare multiple variables at the same time.
- A variable name can contain letters, digits, and underscores `(_)`, and it must start with a letter or an underscore.
**Identifiers**: Unique names given to variables so they can be recognized individually in a program.
**Constants**: Values that do not change during program execution.
```C++
#include <iostream>
using namespace std;

int main()
{
    // Declaring variables
    int age = 20;
    double height = 5.7;
    char grade = 'A';
    string name = "John";

    // Printing variable values
    cout << "Name: " << name << endl;
    cout << "Age: " << age << endl;
    cout << "Height: " << height << endl;
    cout << "Grade: " << grade << endl;

    return 0;
}
```
## Data Types
- [Data types](https://www.geeksforgeeks.org/cpp/cpp-data-types/) define the type of data a variable can store. Every variable in C++ must have a data type.
- C++ is a statically typed language, which means the data type of a variable is fixed at compile time and cannot change later.
	### Types of Data Types in C++ 
	1. **Integer (int)** 
		- Stores whole numbers (e.g., 10, -5, 0). Can be used for counting, indexing, or arithmetic operations.
		- Integers take 4 bytes of memory.
	 2. **Floating Point (float)**
		- Stores decimal numbers with single precision (e.g., 3.14). Useful for measurements, fractions, and approximate calculations.
		- It takes 4 bytes of memory.
	3. **Double (double)**
		- Stores decimal numbers with double precision (more accurate than float, e.g., 3.14159). Used when more precision is required in calculations.
		- It takes 8 bytes of memory.
	 4. **Character (char)** 
		 - Stores a single character (e.g., 'A', 'b', '9'). Usually enclosed in single quotes and can be used in text processing.
		- It takes 1 byte of memory.
	5. **Boolean (bool)** 
		- Stores only `true` or `false` values. Commonly used in conditions and logical operations.
		- It takes 1 byte of memory.
	6. **String (string)** 
		- Stores a sequence of characters (e.g., "Hello"). Used for text, names, messages, or sentences.
		- We have to `include <string>` header file for using string class. 
		- However, because strings are, in fact, sequences of characters, we can represent them also as plain arrays of elements of a character type.
Test strings 
```C++
// Header file for input and output
#include <iostream>
#include <string>
// To avoid using std:: before cout and cin
using namespace std;

// Main function - entry point of every C++ program
int main()
{
    // Display output on the screen
    cout << "Hello, stranger" << endl;

    // Take input from the user
    string name;
    cout << "What's is your name?";
    cin >> name;

    // Display the entered number
    cout << "Nice to meet you " << name << endl;

    // Indicates successful program execution
    return 0;
}
```
## Conditional Statements
- [Conditional statements](https://www.geeksforgeeks.org/cpp/decision-making-c-cpp/) allow us to control the flow of the program based on certain conditions.
- It helps us to run a specific section of code based on a condition.
### Types of conditional statements
1. if statement
```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 10;

    // If statement
    if (i < 15)
    {
        cout << "10 is less than 15";
    }

    return 0;
}
```
2. if-else statement
```cpp
#include <iostream>
using namespace std;

int main()
{
    int i = 10;

    // If statement
    if (i < 15)
    {
        cout << "10 is less than 15";
    }

    // Else statement with the above if
    else
    {
        cout << "10 is not less than 15";
    }

    return 0;
}
```
2. else if statements:
```cpp
#include <stdio.h>

int main()
{
    int marks = 85;

    // Assign grade based on marks
    if (marks >= 90)
    {
        printf("A\n");
    }
    else if (marks >= 80)
    {
        printf("B\n");
    }
    else if (marks >= 70)
    {
        printf("C\n");
    }
    else if (marks >= 60)
    {
        printf("D\n");
    }
    else
    {
        printf("F\n");
    }

    return 0;
}
```
4. swich statement 
	-  Executes one block out of many based on a variable’s value.
	- Each case must have a [break](https://www.geeksforgeeks.org/cpp/cpp-break-statement/) to stop execution after a match.
	- Useful when there are fixed known options.
```cpp
#include <iostream>
using namespace std;

int main()
{

    // Variable to the used as switch expression
    char x = 'A';

    // Switch statement with three cases
    switch (x)
    {
    case 'A':
        cout << "A";
        break;
    case 'B':
        cout << "B";
        break;
    default:
        cout << "Other than A and B";
        break;
    }
    return 0;
}
```
5. Shorthand if else (**[[Ternary Operator]]**)
- [Ternary operator](https://www.geeksforgeeks.org/cpp/cpp-ternary-or-conditional-operator/) (?:) is a short-hand for simple if-else statements.
- It evaluates a condition and returns one value if true and another if false.
```cpp
#include <iostream>
using namespace std;

int main()
{
    int x = 10, y = 20;

    // Using ternary operator
    int max_val = (x > y) ? x : y;

    cout << "The maximum value is " << max_val;
    return 0;
}
```
- Here, two integers *x* and *y* are initialized to 10 and *20*, respectively. The ternary operator *(x > y) ? x : y* checks whether *x* is greater than *y*. If true, it assigns *x* to *max_val*. Otherwise, it assigns *y*. Since *y* is greater, *max_val* becomes *20*.
- expression ****?**** statement_1 executed when  expression is true: statement_2 executed when expression is false
## Loops
- [Loops](https://www.geeksforgeeks.org/cpp/cpp-loops/) are used to repeat a block of code multiple times until a condition is met.
- They save time and effort by avoiding writing the same code again and again.
#### Types of Loops
1. **For loop** repeats a block of code a fixed number of times.
	-  [for loop](https://www.geeksforgeeks.org/cpp/cpp-for-loop/) repeats a block of code a fixed number of times.
	- Usually has initialization, condition, and increment/decrement in one line
	- Best used when the number of iterations is known
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // for loop to print "Hi" 5 times
    for (int i = 5; i < 10; i++)
    {
        cout << "Hi" << endl;
    }

    return 0;
}
```
2. **While Loop**
- [for loop](https://www.geeksforgeeks.org/cpp/cpp-for-loop/) repeats a block of code a fixed number of times.
- Usually has initialization, condition, and increment/decrement in one line.
- Best used when the number of iterations is known.
```cpp
#include <iostream>
using namespace std;

int main()
{

    // while loop to print numbers from 1 to 5
    int i = 0;
    while (i < 5)
    {
        cout << "Hi" << endl;
        i++;
    }

    return 0;
}
```
3. **Do-While Loop**
- It is similar to while loop, but executes the code at least once.
- The condition is checked before executing the code.
- Best used when the number of iterations is not known in advance.
```cpp
#include <iostream>
using namespace std;

int main()
{

    // do-while loop to print "Hi" 5 times
    int i = 0;
    do
    {
        cout << "Hi" << endl;
        i++;
    } while (i < 5);

    return 0;
}
```
## Arrays
```cpp
#include <iostream>
using namespace std;

int main()
{
    // declaring and initializing an array of size 5
    int arr[5] = {2, 4, 8, 12, 16};

    // printing array elements
    for (int i = 0; i < 5; i++)
    {
        cout << arr[i] << " ";
    }

    return 0;
}
```
## Multi-dimensional Arrays
Multidimensional arrays can be described as "arrays of arrays"
- The most common type is a 2D array, which can be thought of as a table or matrix with rows and columns.
- Values are accessed using multiple indices, e.g., array[row][column]
```cpp
#include <iostream>
using namespace std;

int main()
{

    // declaring and initializing a 2D array
    // with 3 rows and 4 columns
    int matrix[3][4] = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};

    // printing the elements of the 2D array
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 4; j++)
        {
            cout << matrix[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
## Vectors
- A [vector](https://www.geeksforgeeks.org/cpp/vector-in-cpp-stl/) is a dynamic array that can grow or shrink in size automatically.
- It is part of the C++ Standard Template Library ([STL](https://www.geeksforgeeks.org/cpp/the-c-standard-template-library-stl/)), so you need `#include <vector>`.
- Elements in a vector are accessed using indices just like arrays\
- Vectors provide useful functions like [push_back()](https://www.geeksforgeeks.org/cpp/vector-push-back-cpp-stl/), [pop_back()](https://www.geeksforgeeks.org/cpp/vector-pop-back-in-cpp-stl/), [size()](https://www.geeksforgeeks.org/cpp/vector-size-in-cpp-stl/), and [clear()](https://www.geeksforgeeks.org/cpp/vector-clear-in-cpp-stl/).
```cpp
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    // Declares an empty vector
    vector<int> v1;
    // Declares vector with given size
    // and fills it with a value
    vector<int> v2(3, 5);
    // Print items of v2
    for (int x : v2)
    {
        cout << x << " ";
    }
    cout << endl;
    // Initializes vector using initializer list.
    vector<int> v3 = {1, 2, 3};
    // Print items of v3
    for (int x : v3)
    {
        cout << x << " ";
    }
    return 0;
}
```
## References
- A [reference](https://www.geeksforgeeks.org/cpp/references-in-cpp/) is an alias for another variable, meaning it refers to the same memory location.
- Once a reference is initialized, it cannot be changed to refer to another variable.
```cpp
#include <iostream>
using namespace std;

int main()
{
    int x = 10;
    // ref is a reference to x.
    int &ref = x;
    // printing value using ref
    cout << ref << endl;
    // Changing the value and printing again
    ref = 22;
    cout << ref;
    return 0;
}
```
## Pointers
- A [pointer](https://www.geeksforgeeks.org/cpp/cpp-pointers/) is a variable that stores the memory address of another variable.
- Pointers can be reassigned to point to different variables.
```cpp
#include <iostream>
using namespace std;

int main()
{
    int var = 10;

    // declare pointer and store address of x
    int *ptr = &var;

    // print value and address
    cout << "Value of x: " << var << endl;
    cout << "Address of x: " << &var << endl;
    cout << "Value stored in pointer ptr: " << ptr << endl;
    cout << "Value pointed to by ptr: " << *ptr << endl;

    return 0;
}
```
Output:
`Value of x: 10
`Address of x: 0x7ffed805557c`
`Value stored in pointer ptr: 0x7ffed805557c`
`Value pointed to by ptr: 10`
### Pointers and arrays
The concept of arrays is related to that of pointers. In fact, arrays work very much like pointers to their first elements, and, actually, an array can always be implicitly converted to the pointer of the proper type. For example, consider these two declarations:
```cpp
int myarray [20];
int * mypointer;
```
The following assignment operation would be valid:
```cpp
mypointer = myarray;
```
bu not the other way arround. A pointer can be assigned a different address, whereas an array can never be assigned anything. Alwas represent the same block of 20 elements.
### Pointer arithmetics
Suppose now that we define three pointers in this compiler:
```cpp
char *mychar; // located at 1000, size 1 byte
short *myshort; // located at 2000, size 2 bytes
long *mylong; // located at 3000, size 4 bytes
```
 - pointing to locations 1000, 2000 and 3000
 ```cpp
++mychar; // now located at 1001
++myshort;// now located at 2002
++mylong;// now located at 3004
```
The reason is that, when adding one to a pointer, the pointer is made to point to the following element of the same type, and, therefore, the size in bytes of the type it points to is added to the pointer. This is applicable both when adding and subtracting any number to a pointer. Also when f.e. `myshort = muchort +1`

Regarding the increment (`++`) and decrement (`--`) operators, they both can be used as either prefix or suffix of an expression, with a slight difference in behavior: as a prefix, the increment happens before the expression is evaluated, and as a suffix, the increment happens after the expression is evaluated.
Essentially, these are the four possible combinations of the dereference operator with both the prefix and suffix versions of the increment operator (the same being applicable also to the decrement operator):
```cpp
*p++   // same as *(p++): post-increment pointer, and dereference unincremented address
*++p   // same as *(++p): increment pointer, and dereference incremented address
++*p   // same as ++(*p): dereference pointer, and increment the value it points to
(*p)++ // dereference pointer, and post-increment the value it points to 
```
Check [online](https://cplusplus.com/doc/tutorial/pointers/) for 
- Pointers and const
- Pointers and string literals
- Pointers to pointers
- Invalid pointers and null pointers

## Functions
- A [function](https://www.geeksforgeeks.org/cpp/functions-in-cpp/) is a block of code designed to perform a specific task.
- It helps to avoid repeating code and make programs organized and readable.
- A function can take inputs (parameters) and [return](https://www.geeksforgeeks.org/cpp/return-statement-in-cpp-with-examples/) a value, but both are optional.
`type name ( parameter1, parameter2, ...) { statements }   `  
Where:  
- `type` is the type of the value returned by the function.  Functions with no type: void
- `name` is the identifier by which the function can be called.  
- `parameters` (as many as needed): Each parameter consists of a type followed by an identifier, with each parameter being separated from the next by a comma. Each parameter looks very much like a regular variable declaration (for example: `int x`), and in fact acts within the function as a regular variable which is local to the function. The purpose of parameters is to allow passing arguments to the function from the location where it is called from.  
- `statements` is the function's body. It is a block of statements surrounded by braces { } that specify what the function actually does.
- Functions are called/invoked whenever you need to execute that task
```cpp
#include <iostream>
using namespace std;

// Function declaration and definition
void greet()
{
    cout << "Hello, World!" << endl;
}

int main()
{
    
    // Calling the function
    greet(); 
    
    return 0;
}
```
## String Functions
There are several string functions present in Standard Template Library in C++ that are used to perform operations on strings. Some of the commonly used string functions are:
1. **length()**
```cpp
#include <iostream>
#include <string>
using namespace std;

int main()
{
    // Declare a string
    string name = "GeeksforGeeks";

    // Find and print the length of the string
    cout << "The length of the name is: " << name.length() << endl;

    return 0;
}
``` 
2. **substr()**
- It is used to extract a [substring](https://www.geeksforgeeks.org/cpp/substring-in-cpp/) from a given string.
```cpp
#include <iostream>
#include <string>
using namespace std;
int main()
{
    string str = "GeeksforGeeks";

    // Extracts a substring starting from
    // index 1 with a length of 5
    string sub = str.substr(1, 5);

    cout << "Substring: " << sub << endl;

    return 0;
}
```
 3. **append()**
 ```cpp
#include <iostream>
#include <string>
using namespace std;
int main() {
    string str = "Geeksfor";

    str.append("Geeks");

    cout << "Appended string: " << str << endl;

    return 0;
}
 ```
4. **compare()**
 - It is used to [compare](https://www.geeksforgeeks.org/cpp/stdstringcompare-in-c/) two strings lexicographically.
```cpp
#include <iostream>
#include <string>
using namespace std;
int main()
{
    string str1 = "Geeks";
    string str2 = "for";
    string str3 = "Geeks";

    int result1 = str1.compare(str2);
    cout << "Comparison result: " << result1 << endl;

    int result2 = str1.compare(str3);
    cout << "Comparison result: " << result2 << endl;

    return 0;
}
```
5. **empty()**
- It is used to check if a string is [empty](https://www.geeksforgeeks.org/cpp/std-string-empty-in-cpp/).
```cpp
#include <iostream>
using namespace std;

int main()
{
    string str1 = "GeeksforGeeks";
    string str2 = "";

    if (str1.empty())
        cout << "str1 is empty" << endl;
    else
        cout << "str1 is not empty" << endl;

    if (str2.empty())
        cout << "str2 is empty" << endl;
    else
        cout << "str2 is not empty" << endl;
    return 0;
}
```
## Math Functions
| Function      | Description                                                | Example                         |
| ------------- | ---------------------------------------------------------- | ------------------------------- |
| **min(x, y)** | Returns the minimum value of x and y.                      | cout << min(10, 20);            |
| **max(x,y)**  | Returns the maximum value of x and y.                      | cout << max(10, 20);            |
| **sqrt(x)**   | Returns the square root of x.                              | cout << sqrt(25);               |
| **ceil(x)**   | It rounds up the value x to its nearest integer.           | double ceilX = ceil(3.14159);   |
| **floor(x)**  | It rounds the value of x downwards to the nearest integer. | double floorX = floor(3.14159); |
| **pow(x,n)**  | It returns the value x raised to the power of y            | double result = pow(3.0, 2.0);  |
## Object-Oriented Programming (OOP)
Object-oriented programming generally means storing data in the form of classes and objects.
### Class and Objects
- [Class:](https://www.geeksforgeeks.org/cpp/c-classes-and-objects/) A class is a user-defined data type that contains its data members and member functions. A class is a blueprint for objects having similar attributes and behavior.
- **Objects:** An object is an instance or a variable of the class.
### Pillars of OOPs
1. **Encapsulation** 
	- It means bundling data (variables) and functions (methods) together in a class.
	- It hides the internal details of an object from the outside world (data hiding).
	- Access to data is provided through public functions (getters/setters).
	- Helps in preventing accidental modification of important data.
2. **Abstraction**
	- It is hiding complex implementation details and showing only the necessary features.
	- It helps in simplifying the program for the user.
	- Achieved in C++ using abstract classes and pure virtual functions
	- *Example: A car driver knows how to drive, but doesn’t need to know the engine details.*
3. **Inheritance**
	- It allows a class (child/derived class) to acquire properties and behavior of another class (parent/base class).
	- Promotes code reusability.
	- Types in C++: single, multiple, multilevel, hierarchical, hybrid.
	- *Example: A car class can inherit from a Vehicle class to reuse common features.*
 4. **Polymorphism**
	 - It means one entity can take many forms.
	- Two types: Compile-time (function overloading, operator overloading) , Run-time (virtual functions)
	- Helps in using the same interface for different types of objects.
	- *Example: A print() function can behave differently for int, float, or string.*
## File Handling
- **File handling** means reading data from a file and manipulating the data of a file.
	### File Handling Operations
	1. Open a file: We can use `open()` member function of `ofstream class` to open a file
	2. Read a file: We can use `getline()` member function of `ifstream class` to read a file
	3. Write to a file: We can use `<< operator` to write to a file after opening a file with the object `of ofstream` class.
```cpp
#include <fstream>
#include <iostream>
#include <string>

using namespace std;

int main()
{
    ofstream outputFile("example.txt");

    // Open the file for writing
    outputFile.open("example.txt");
    if (outputFile.is_open()) {

        // Write data to the file
        outputFile << "Hello, World!" << endl;
        outputFile << 42 << endl;
        outputFile.close(); // Close the file
    }
    else {

        // Failed to open the file
        cout << "Error opening the file for writing."
             << endl;
        return 1;
    }

    // Reading from a file
    ifstream inputFile("example.txt");
    if (inputFile.is_open()) {
        string line;
        while (getline(inputFile, line)) {
            // Print each line
            cout << line << endl;
        }
        // Close the file
        inputFile.close();
    }
    else {

        // Failed to open the file
        cout << "Error opening the file for reading."
             << endl;
        return 1;
    }

    return 0;
}
```
This C++ cheat sheet can serve as a reference guide for programmers that provides quick access to concepts of C++