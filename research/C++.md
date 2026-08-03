---
tags:
  - status/wip
  - type/commands
  - topic/coding/cplusplus
aliases:
date:
---
# [Git C++ Handson training](https://github.com/hsf-training/cpluspluscourse/blob/master/exercises/ExerciseSchedule_EssentialCourse.md)
# [[Summary C++ Cheatsheet]]

![[Screenshot 2026-03-09 at 11.29.30.png|502]]
# Biggest Thing in C++ and C
- managing memory 
- never delete used memory 
- Alocate
- Have two vectors pointing to one place in memory 
- Smart pointers will help to take care of the memory managing
- 


Constructors and Deconstructors

# Tutorial
Taken from [link](https://cplusplus.com/doc/tutorial/)
- up to Dynamic memory
## Compilers
```machine code
000001001111000001111101000001010011110000111101010000100101111110010100000000
```
vs 
```c++
int a, b, sum;
     
cin >> a;
cin >> b;
             
sum = a + b;
cout << sum << endl;
```
For the translation c++ needs a set of tools, known as the development toolchain, whose core are a compiler and its linker
- ### Console programs
	- If you happen to have a Linux or Mac environment with development features, you should be able to compile any of the examples directly from a terminal just by including C++11 flags in the command for the compiler
	- **Clang** OS X, among others...
 ```shell
	- clang++ -std=c++11 -stdlib=libc++ example.cpp -o example_program`
```
- `clang++` is the compiler 
- followed by specificatons of the c++ version 
- Program name -o compiled_program
- the compiled program can be run by `./<compiled_program>`
## Structure of a program
- learning by writing - Hello World
```C++
// my first program in c++
#include <iostream>

int main()
{
	std::cout << "Hello World!";
}
```
- // - comment - `/* block comment*/`
- Line 2: `#include <iostream>`
	Lines beginning with a hash sign (`#`) are directives read and interpreted by what is known as the _preprocessor_. They are special lines interpreted before the compilation of the program itself begins. In this case, the directive `#include <iostream>`, instructs the preprocessor to include a section of standard C++ code, known as _header iostream_, that allows to perform standard input and output operations, such as writing the output of this program (Hello World) to the screen.
- Line 4: `int main (){  ....   }`
	This line initiates the declaration of a function. Essentially, a function is a group of code statements which are given a name: in this case, this gives the name "main" to the group of code statements that follow. Functions will be discussed in detail in a later chapter, but essentially, their definition is introduced with a succession of a type (`int`), a name (`main`) and a pair of parentheses (`()`), optionally including parameters. 
	{marks the beginning of the function and }  marks the end of the funcion
	The function named `main` is a special function in all C++ programs; it is the function called when the program is run. The execution of all C++ programs begins with the `main` function, regardless of where the function is actually located within the code.
- Line 6: `std::cout << "Hello World!";`
	This line is a C++ statement. A statement is an expression that can actually produce some effect. It is the meat of a program, specifying its actual behavior. Statements are executed in the same order that they appear within a function's body.  
	This statement has three parts: First, `std::cout`, which identifies the **st**andar**d** **c**haracter **out**put device (usually, this is the computer screen). Second, the insertion operator (`<<`), which indicates that what follows is inserted into `std::cout`. Finally, a sentence within quotes ("Hello world!"), is the content inserted into the standard output.    
	Notice that the statement ends with a semicolon (`;`). This character marks the end of the statement, just as the period ends a sentence in English. All C++ statements must end with a semicolon character. One of the most common syntax errors in C++ is forgetting to end a statement with a semicolon.
### Using namespace std
- `cout` being used instead of `std::cout`. 
	-  _unqualified name_ (`cout`) - part of the standard library 
	- the second qualifies it directly within the _namespace_ `std` (as `std::cout`).
		- declares the standard C+ - library 
	- qualify each and every use of elements of the library as we have done by prefixing `cout` with `std::`
	- or introduce visibility of its components. The most typical way to introduce visibility of these components is by means of _using declarations_: `using namespace std;` right after the `#include ...commands`
## Variables and types
- Variables are portions of memory to store a value (`a = 1`).
- Each variable needs a name that identifies it and distinguishes it from the others
- **Identifiers** f.e. `a` 
- Identifiers that can **not** be used are:
	- `alignas, alignof, and, and_eq, asm, auto, bitand, bitor, bool, break, case, catch, char, char16_t, char32_t, class, compl, const, constexpr, const_cast, continue, decltype, default, delete, do, double, dynamic_cast, else, enum, explicit, export, extern, false, float, for, friend, goto, if, inline, int, long, mutable, namespace, new, noexcept, not, not_eq, nullptr, operator, or, or_eq, private, protected, public, register, reinterpret_cast, return, short, signed, sizeof, static, static_assert, static_cast, struct, switch, template, this, thread_local, throw, true, try, typedef, typeid, typename, union, unsigned, using, virtual, void, volatile, wchar_t, while, xor, xor_eq`
- The C++ language is a "case sensitive" language. That means that an identifier written in capital letters is not equivalent to another one with the same name but written in small letters. Thus, for example, the `RESULT` variable is not the same as the `result` variable or the `Result` variable. These are three different identifiers identifiying three different variables
### Fundamental data types
- What the program needs to be aware of is the kind of data stored in the variable. It's not the same to store a simple integer as it is to store a letter or a large floating-point number; even though they are all represented using zeros and ones, they are not interpreted in the same way, and in many cases, they don't occupy the same amount of memory.
- **Character types:** represent  a single character, such as `'A'` or `'$'`
- **Numerical integer types**  whole number value either _signed_ or _unsigned_,
- **Floating-point types** with different levels of precision, depending on which of the three floating-point types is used.
- **Boolean type** `true` or `false`

| Group                    | Type names*                  | Notes on size / precision                          |
| ------------------------ | ---------------------------- | -------------------------------------------------- |
| Character types          | char                         | Exactly one byte in size. At least 8 bits.         |
| Character types          | char16_t                     | Not smaller than `char`. At least 16 bits.         |
| Character types          | char32_t                     | Not smaller than `char16_t`. At least 32 bits.     |
| Character types          | wchar_t                      | Can represent the largest supported character set. |
| Integer types (signed)   | signed char                  | Same size as `char`. At least 8 bits.              |
| Integer types (signed)   | _signed_ **short** _int_     | Not smaller than `char`. At least 16 bits.         |
| Integer types (signed)   | _signed_ **int**             | Not smaller than `short`. At least 16 bits.        |
| Integer types (signed)   | _signed_ **long** _int_      | Not smaller than `int`. At least 32 bits.          |
| Integer types (signed)   | _signed_ **long long** _int_ | Not smaller than `long`. At least 64 bits.         |
| Integer types (unsigned) | **unsigned char**            | (same size as their signed counterparts)           |
| Integer types (unsigned) | **unsigned short** _int_     |                                                    |
| Integer types (unsigned) | **unsigned** _int_           |                                                    |
| Integer types (unsigned) | **unsigned long** _int_      |                                                    |
| Integer types (unsigned) | **unsigned long long** _int_ |                                                    |
| Floating-point types     | **float**                    |                                                    |
| Floating-point types     | **double**                   | Precision not less than `float`                    |
| Floating-point types     | **long double**              | Precision not less than `double`                   |
| Boolean type             | **bool**                     |                                                    |
| Void type                | **void**                     | no storage                                         |
| Null pointer             | **decltype(nullptr)**        |                                                    |

Type sizes above are expressed in bits; the more bits a type has, the more distinct values it can represent, but at the same time, also consumes more space in memory:

|Size|Unique representable values|Notes|
|---|---|---|
|8-bit|`256`|= 28|
|16-bit|`65 536`|= 216|
|32-bit|`4 294 967 296`|= 232 (~4 billion)|
|64-bit|`18 446 744 073 709 551 616`|= 264 (~18 billion billion)|
### Initialization of variables 
3 types valid and equivalent:

`type identifier = initial_value;`  
For example, to declare a variable of type `int` called `x` and initialize it to a value of zero from the same moment it is declared, we can write:  `int x = 0;`
  
A second method, known as _constructor initialization_ (introduced by the C++ language), encloses the initial value between parentheses (`()`):  
`type identifier (initial_value);`  
For example: `int x(0);`
  
Finally, a third method, known as _uniform initialization_, similar to the above, but using curly braces (`{}`) instead of parentheses (this was introduced by the revision of the C++ standard, in 2011):  
`type identifier {initial_value};`  
For example:  
`int x{0};`

### Type deduction: auto and decltype
```cpp
int foo = 0;
auto bar = foo;  // the same as: int bar = foo;
```

```cpp
int foo = 0;
decltype(foo) bar;  // the same as: int bar;
```


Unsigned may be combined with any of the other two in any order to form `unsigned long` or `unsigned long long`.  
  
For example:  
```
75         // int
75u        // unsigned int
75l        // long
75ul       // unsigned long 
75lu       // unsigned long 
```
The default type for floating-point literals is `double`. Floating-point literals of type `float` or `long double` can be specified by adding one of the following suffixes:
```
f or F // float
l or L // long double
```
Any of the letters that can be part of a floating-point numerical constant (`e`, `f`, `l`) can be written using either lower or uppercase letters with no difference in meaning.

**Character and string literals**
Notice that to represent a **single character,** we enclose it between **single quotes (`'`)**, and to express a **string** (which generally consists of more than one character), we enclose the characters **between double quotes (`"`).**

Character and string literals can also represent special characters that are difficult or impossible to express otherwise in the source code of a program, like newline (`\n`) or tab (`\t`). These special characters are all of them preceded by a backslash character (`\`).
Here you have a list of the single character escape codes:  

|Escape code|Description|
|---|---|
|`\n`|newline|
|`\r`|carriage return|
|`\t`|tab|
|`\v`|vertical tab|
|`\b`|backspace|
|`\f`|form feed (page feed)|
|`\a`|alert (beep)|
|`\'`|single quote (`'`)|
|`\"`|double quote (`"`)|
|`\?`|question mark (`?`)|
|`\\`|backslash (`\`)|
Some programmers also use a trick to include long string literals in multiple lines: In C++, a backslash (`\`) at the end of line is considered a _line-continuation_ character that merges both that line and the next into a single line.

Three keyword literals exist in C++: `true`, `false` and `nullptr`:
- `true` and `false` are the two possible values for variables of type `bool`.
- `nullptr` is the _null pointer_ value.
### Preprocessor definitions (#define)
Another mechanism to name constant values is the use of preprocessor definitions. They have the following form:  
`#define identifier replacement`  
**DO NOT require semicolons (;) at the end; the directive extends automatically until the end of the line**
After this directive, any occurrence of `identifier` in the code is interpreted as `replacement`, where replacement is any sequence of characters (until the end of the line). This replacement is performed by the preprocessor, and happens before the program is compiled, thus causing a sort of blind replacement: the validity of the types or syntax involved is not checked in any way.  
For example:
```cpp
#include <iostream>
using namespace std;

#define PI 3.14159
#define NEWLINE '\n'

int main ()
{
  double r=5.0;               // radius
  double circle;

  circle = 2 * PI * r;
  cout << circle;
  cout << NEWLINE;

}
```
### Logical operators ( !, &&, || )
The logical operators `&&` and `||` are used when evaluating two expressions to obtain a single relational result.
The operator `&&` corresponds to the Boolean logical operation AND, which yields `true` if both its operands are `true`, and `false` otherwise. The following panel shows the result of operator `&&` evaluating the expression `a&&b`:
The operator `||` corresponds to the Boolean logical operation OR, which yields `true` if either of its operands is `true`, thus being false only when both operands are false. Here are the possible results of `a||b`:

When using the logical operators, C++ only evaluates what is necessary from left to right to come up with the combined relational result, ignoring the rest. Therefore, in the last example (`(5==5)||(3>6)`), C++ evaluates first whether `5==5` is `true`, and if so, it never checks whether `3>6`is `true` or not. This is known as _short-circuit evaluation_, and works like this for these operators:

### Conditional ternary operator ( ? )
The conditional operator evaluates an expression, returning  `value1` if that expression evaluates to `true`, and `value2` if the expression evaluates as `false`. Its syntax is:
`condition ? value1:value2` 

### Comma operator ( , )
The comma operator (`,`) is used to separate two or more expressions that are included where only one expression is expected. When the set of expressions has to be evaluated for a value, only the right-most expression is considered.  
For example, the following code: 
```
a = (b=3, b+2);
```
would first assign the value `3` to `b`, and then assign `b+2` to variable `a`. So, at the end, variable `a` would contain the value `5` while variable `b` would contain value `3`.

### Bitwise operators ( &, |, ^, ~, <<, >> )
Bitwise operators modify variables considering the bit patterns that represent the values they store.  

| operator | asm equivalent | description                      |
| -------- | -------------- | -------------------------------- |
| `&`      | `AND`          | Bitwise AND                      |
| `\|`     | `OR`           | Bitwise inclusive OR             |
| `^`      | `XOR`          | Bitwise exclusive OR             |
| `~`      | `NOT`          | Unary complement (bit inversion) |
| `<<`     | `SHL`          | Shift bits left                  |
| `>>`     | `SHR`          | Shift bits right                 |
## Basic Input/Output
C++ uses a convenient abstraction called _streams_ to perform input and output operations in sequential media such as the screen, the keyboard or a file.
A *stream* is an entity where a program can either insert or extract characters to/from.
The standard library defines a handful of stream objects that can be used to access what are considered the standard sources and destinations of characters by the environment where the program runs:

|stream|description|
|---|---|
|`cin`|standard input stream|
|`cout`|standard output stream|
|`cerr`|standard error (output) stream|
|`clog`|standard logging (output) stream|
### Standard output (cout)
```cpp
cout << "Output sentence"; // prints Output sentence on screen
cout << 120;               // prints number 120 on screen
cout << x;                 // prints the value of x on screen 
```

The `endl` manipulator can also be used to break lines. For example:
```cpp
cout << "First sentence." << endl;
cout << "Second sentence." << endl;
```

### Standard input (cin)
```cpp
int age;
cin >> age;
```
The first statement declares a variable of type `int` called `age`, and the second extracts from `cin` a value to be stored in it. 
This operation makes the program wait for input from `cin`; generally, this means that the program will wait for the user to enter some sequence with the keyboard.
In this case, note that the characters introduced using the keyboard are only transmitted to the program when the ENTER (or RETURN) key is pressed. Once the statement with the extraction operation on `cin` is reached, the program will wait for as long as needed until some input is introduced.
#### cin and strings
```cpp
string mystring;
cin >> mystring;
```
Only a single word as spaces are concidered terminating the value being extracted

For entire lines: Funktion `getline()`
```cpp
// cin with strings
#include <iostream>
#include <string>
using namespace std;

int main ()
{
  string mystr;
  cout << "What's your name? ";
  getline (cin, mystr);
  cout << "Hello " << mystr << ".\n";
  cout << "What is your favorite team? ";
  getline (cin, mystr);
  cout << "I like " << mystr << " too!\n";
  return 0;
}
```
#### stringstream
- To convert a string to an integer
```cpp
string mystr ("1204");
int myint;
stringstream(mystr) >> myint;
```

## Loops and If statements - in [[Summary C++ Cheatsheet]]
#### for loops
```cpp
for (n=0, i=100; n!=i; ++n, --i)
```
Initialization; Condition; Increase
`n` starts with a value of 0, and `i` with 100, the condition is `n!=i` (i.e., that `n` is not equal to `i`). Because `n` is increased by one, and `i` decreased by one on each iteration, the loop's condition will become false after the 50th iteration, when both `n` and `i` are equal to 50.
##### Range-based for loop
The for-loop has another syntax, which is used exclusively with ranges:  
`for ( declaration : range ) statement;`
This kind of for loop iterates over all the elements in `range`, where `declaration` declares some variable able to take the value of an element in this range.

An example of range-based for loop using strings:
```cpp
// range-based for loop
#include <iostream>
#include <string>
using namespace std;

int main ()
{
  string str {"Hello!"};
  for (char c : str)
  {
    cout << "[" << c << "]";
  }
  cout << '\n';
}
```
Can also be written as `for (auto c: str) cout << "[" << c << "]";`

#### Jump statements
Jump statements allow altering the flow of a program by performing jumps to specific locations.
**break**
- leaves a loop
```cpp
// break loop example
#include <iostream>
using namespace std;

int main ()
{
  for (int n=10; n>0; n--)
  {
    cout << n << ", ";
    if (n==3)
    {
      cout << "countdown aborted!";
      break;
    }
  }
}
```
**continue**
- skips the rest of the loop 
**goto statement**
- allows to make an abolute jump to another point in the program 
- the destination point is identified by an label `label:`
```cpp
#include <iostream>
using namespace std;

int main ()
{
	int n=10
mylabel:
	count << n << ", "
	n--;
	if (n>0) goto mylabel;
	cout << "liftoff!\n"	
}
```
## Functions in [[Summary C++ Cheatsheet]]
#### Recursivity 
Recursivity is the property that functions have to be called by themselves. It is useful for some tasks, such as sorting elements, or calculating the factorial of numbers.
$n! = n * (n-1) * (n-2) * (n-3) ... * 1$
```cpp
// factorial calculator
#include <iostream>
using namespace std;

long factorial (long a)
{
  if (a > 1)
   return (a * factorial (a-1));
  else
   return 1;
}

int main ()
{
  long number = 9;
  cout << number << "! = " << factorial (number);
  return 0;
}
```
Notice how in function factorial we included a call to itself, but only if the argument passed was greater than 1, since, otherwise, the function would perform an infinite recursive loop, in which once it arrived to 0, it would continue multiplying by all the negative numbers (probably provoking a stack overflow at some point during runtime).

### Overloaded functions
In C++, two different functions can have the same name if their parameters are different; either because they have a different number of parameters, or because any of their parameters are of a different type.
```cpp
// overloading functions
#include <iostream>
using namespace std;

int operate (int a, int b)
{
  return (a*b);
}

double operate (double a, double b)
{
  return (a/b);
}

int main ()
{
  int x=5,y=2;
  double n=5.0,m=2.0;
  cout << operate (x,y) << '\n';
  cout << operate (n,m) << '\n';
  return 0;
}
```
### Function templates
- overloaded functions that are defined in the same way just for different types
For cases such as this, C++ has the ability to define functions with generic types, known as _function templates_. Defining a function template follows the same syntax as a regular function, except that it is preceded by the `template` keyword and a series of template parameters enclosed in angle-brackets <>
`template <template-parameters> function-declaration`
For example
```cpp
template <class SomeType>
SomeType sum (SomeType a, SomeType b)
{
  return a+b;
}
```
Instantiating a template is applying the template to create a function using particular types or values for its template parameters. This is done by calling the _function template_, with the same syntax as calling a regular function, but specifying the template arguments enclosed in angle brackets:
`name <template-arguments> (function-arguments)`
So for example 
```cpp
x = sum<int>(10,20);
```
Or alternatively 
```cpp
int a=10, b=20, c;
c = sum(a,b)
```
If `sum` is called with arguments of different types, the compiler may not be able to deduce the type of `SomeType` automatically.

Templates are a powerful and versatile feature. They can have multiple template parameters, and the function can still use regular non-templated types. For example:
```cpp
// function templates
#include <iostream>
using namespace std;

template <class T, class U>
bool are_equal (T a, U b)
{
  return (a==b);
}

int main ()
{
  if (are_equal(10,10.0))
    cout << "x and y are equal\n";
  else
    cout << "x and y are not equal\n";
  return 0;
}
```
## Name visibility
#### Scopes
An entity declared outside any block has _global scope_, meaning that its name is valid anywhere in the code. While an entity declared within a block, such as a function or a selective statement, has _block scope_, and is only visible within the specific block in which it is declared, but not outside it.
The visibility of an entity with _block scope_ extends until the end of the block, including inner blocks. Nevertheless, an inner block, because it is a different block, can re-utilize a name existing in an outer scope to refer to a different entity; in this case, the name will refer to a different entity only within the inner block, hiding the entity it names outside. While outside it, it will still refer to the original entity. For example:
```cpp
// inner block scopes
#include <iostream>
using namespace std;

int main () {
  int x = 10;
  int y = 20;
  {
    int x;   // ok, inner scope.
    x = 50;  // sets value to inner x
    y = 50;  // sets value to (outer) y
    cout << "inner block:\n";
    cout << "x: " << x << '\n';
    cout << "y: " << y << '\n';
  }
  cout << "outer block:\n";
  cout << "x: " << x << '\n';
  cout << "y: " << y << '\n';
  return 0;
}
```
#### Namespaces
Only one entity can exist with a particular name in a particular scope. This is seldom a problem for local names, since blocks tend to be relatively short, and names have particular purposes within them, such as naming a counter variable, an argument, etc...
Namespaces allow us to group named entities that otherwise would have _global scope_ into narrower scopes, giving them _namespace scope_. This allows organizing the elements of programs into different logical scopes referred to by names.
The syntax to declare a namespaces is:
```cpp 
namespace identifier
{
  named_entities
}
```
F.e. 
```cpp
namespace myNamespace
{
  int a, b;
}
```
Namespaces are particularly useful to avoid name collisions. For example:
```cpp
// namespaces
#include <iostream>
using namespace std;

namespace foo
{
  int value() { return 5; }
}

namespace bar
{
  const double pi = 3.1416;
  double value() { return 2*pi; }
}

int main () {
  cout << foo::value() << '\n';
  cout << bar::value() << '\n';
  cout << bar::pi << '\n';
  return 0;
}
```
#### using
The keyword `using` introduces a name into the current declarative region (such as a block), thus avoiding the need to qualify the name. For example:
```cpp
// using
#include <iostream>
using namespace std;

namespace first
{
  int x = 5;
  int y = 10;
}

namespace second
{
  double x = 3.1416;
  double y = 2.7183;
}

int main () {
  using first::x;
  using second::y;
  cout << x << '\n';
  cout << y << '\n';
  cout << first::y << '\n';
  cout << second::x << '\n';
  return 0;
}
```
- `using` and `using namespace` have validity only in the same block in which they are stated or in the entire source code file if they are used directly in the global scope. For example, it would be possible to first use the objects of one namespace and then those of another one by splitting the code in different blocks:
#### Namespace aliasing
`namespace new_name = current_name;`
#### The std namespace
`using namespace std;`
Whether the elements in the `std` namespace are introduced with `using` declarations or are fully qualified on every use does not change the behavior or efficiency of the resulting program in any way. It is mostly a matter of style preference, although for projects mixing libraries, explicit qualification tends to be preferred.
### Storage classes
The storage for variables with _global_ or _namespace scope_ is allocated for the entire duration of the program. This is known as _static storage_, and it contrasts with the storage for _local variables_ (those declared within a block)
These use what is known as automatic storage. The storage for local variables is only available during the block in which they are declared; after that, that same storage may be used for a local variable of some other function, or used otherwise.

But there is another substantial difference between variables with _static storage_ and variables with _automatic storage_:  
- Variables with _static storage_ (such as global variables) that are not explicitly initialized are automatically initialized to zeroes.  
- Variables with _automatic storage_ (such as local variables) that are not explicitly initialized are left uninitialized, and thus have an undetermined value (contain just about any value).
### [[Summary C++ Cheatsheet|Datatypes]]: Arrays, Multi-dimensional Arrays, Vectors, References,  Pointers

## Dynamic memory
- Programs sometimes need to dynamically allocate memory, for which the C++ language integrates the operators `new` and `delete`.
### Operators new and new\[ \]
- Dynamic memory is allocated using operator `new`. `new` is followed by a data type specifier and, if a sequence of more than one element is required, the number of these within brackets `[]`. It returns a pointer to the beginning of the new block of memory allocated. Its syntax is:   
```cpp
pointer = new type; //allocate memory to contain one single element of type `type`  
pointer = new type [number_of_elements]; // allocate a block of elements of type `type`, where `number_of_elements` is an integer value representing the amount of these
```
F.e. 
```cpp
int * foo;
foo = new int [5];
```
In this case, the system dynamically allocates space for five elements of type `int`and returns a pointer to the first element of the sequence, which is assigned to `foo`(a pointer). Therefore, `foo` now points to a valid block of memory with space for five elements of type `int`.

## Missing: Data structures and other data types

## Classes
- Classes are an expanded concept of _data structures_: like data structures, they can contain data members, but they can also contain functions as members.
- An object is an instantiation of a class
- In terms of variables, a class would be the type, and an object would be the variable.
- Classes are defined using either keyword 
	- `class`
	- `struct`
```cpp
class class_name {
  access_specifier_1:
    member1;
  access_specifier_2:
    member2;
  ...
} object_names;
```
Where `class_name` is a valid identifier for the class, `object_names` is an optional list of names for objects of this class.
Classes have the same format as plain _data structures_, except that they can also include functions and have these new things called _access specifiers_. An _access specifier_ is one of the following three keywords: `private`, `public` or `protected`. These specifiers modify the access rights for the members that follow them
- `private` members of a class are accessible only from within other members of the same class (or from their _"friends"_).
- `protected` members are accessible from other members of the same class (or from their _"friends"_), but also from members of their derived classes.
- Finally, `public` members are accessible from anywhere where the object is visible.
-  default, all members of a class declared with the `class` keyword have *private* access for all its members. 
```cpp
class Rectangle {
    int width, height;
  public:
    void set_values (int,int);
    int area (void);
} rect;
```
Declares a class (i.e., a type) called `Rectangle` and an object (i.e., a variable) of this class, called `rect`. This class contains four members: two data members of type `int` (member `width` and member `height`) with _private access_ (because private is the default access level) and two member functions with _public access_: the functions `set_values` and `area`, of which for now we have only included their declaration, but not their definition.
After the declarations of `Rectangle` and `rect`, any of the public members of object `rect` can be accessed as if they were normal functions or normal variables, by simply inserting a dot (`.`) between _object name_ and _member name_. This follows the same syntax as accessing the members of plain data structures. For example:
```cpp
rect.set_values (3,4);
myarea = rect.area();
```
SO: 
```cpp
// classes example
#include <iostream>
using namespace std;

class Rectangle {
    int width, height;
  public:
    void set_values (int,int);
    int area() {return width*height;}
};

void Rectangle::set_values (int x, int y) {
  width = x;
  height = y;
}

int main () {
  Rectangle rect;
  rect.set_values (3,4);
  cout << "area: " << rect.area();
  return 0;
}
```

This example reintroduces the _scope operator_ (\:\:`, two colons), seen in earlier chapters in relation to namespaces. Here it is used in the definition of function `set_values` to define a member of a class outside the class itself.
