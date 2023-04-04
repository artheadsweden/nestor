# Nestor Programming Language
## Introduction
Nestor is a general-purpose programming language designed with simplicity, expressiveness, and performance in mind. Drawing inspiration from the clean and elegant syntax of Python, Nestor aims to provide a user-friendly language that is easy to learn and fun to use, while incorporating powerful features from other programming paradigms, such as functional programming and concurrency.

## Overview of Nestor
Nestor is a statically typed and compiled language that balances the benefits of strong type checking with the flexibility of type inference. Its core features include:

 - A simple and intuitive syntax, inspired by Python
 - Immutable types by default, promoting safe and predictable code
 - Functional programming features for more expressive and concise code
 - Strong concurrency features, inspired by goroutines, for efficient parallelism
 - A unified loop construct that simplifies various looping scenarios
 - Rule-based function dispatchers for flexible and modular code organization
 - A rich set of built-in types, including custom integer types, email, password, date, and geo

## Design Goals and Principles
The primary design goals of Nestor are to:

 1. Provide an easy-to-learn and easy-to-read language that enables developers to write clean and maintainable code.
 2. Encourage the use of best practices, such as immutability and functional programming, to reduce the likelihood of bugs and improve code reusability.
 3. Offer strong concurrency features to facilitate efficient parallelism in modern computing environments.
 4. Deliver a comprehensive standard library that supports a wide range of applications and use cases.

To achieve these goals, Nestor adheres to the following design principles:

 - **Simplicity**: Nestor's syntax is designed to be minimal and intuitive, making it easy for developers to understand and write code.
 - **Expressiveness**: The language includes powerful features that enable developers to write concise and expressive code, reducing boilerplate and improving readability.
 - **Safety**: By encouraging the use of immutability and other best practices, Nestor aims to minimize the risk of bugs and promote more predictable and reliable code.
 - **Performance**: Nestor is designed to be efficient and performant, with features that facilitate parallelism and concurrency.

## Key Features
Nestor offers a unique combination of features that set it apart from other programming languages:

 - Ease of use: Nestor is designed to be simple and easy to learn, with a clean and clear syntax that resembles natural language.

 - Strongly-typed: Nestor enforces strict type checking, which can help catch errors during the compile time and reduce runtime errors.

 - Memory management: Nestor provides automatic memory management with epoch-based garbage collection and scoped regions.

 - Concurrency and parallelism: Nestor supports concurrent and parallel programming through the use of agents, allowing for efficient utilization of multicore processors.

 - Rule-based function dispatchers: Nestor allows for creating powerful rule-based function dispatchers that can invoke different functions based on complex conditions.

 - Error handling: Nestor provides a robust error handling system, which enables developers to handle errors gracefully and improve the stability of their programs.

 - Customizability: Nestor allows developers to extend the language by defining their own data types, functions, and operators, making it highly customizable and adaptable to various problem domains.

 - Portability: Nestor programs can be easily compiled to different platforms, making it a portable and versatile language choice.

As you explore the Nestor programming language, you will discover a versatile and powerful tool for a wide range of applications, from small scripts to large, complex software systems.

## Language Syntax
Nestor's syntax is designed to be simple, clean, and easy to read. It is heavily inspired by Python, with some modifications and enhancements to align with the language's design goals and principles.

## Basic Syntax Rules
 **Indentation**: Nestor uses indentation to define code blocks, similar to Python. Each code block should be indented using a consistent number of spaces (typically 4). Using a mix of spaces and tabs is discouraged.

 **Comments**: Single-line comments in Nestor start with the # character. Everything after the # on the same line will be considered a comment and ignored by the compiler. For multi-line comments, use the /* and */ delimiters, enclosing the comment text between them. 
 ```python
 # This is a single-line comment

 /*
   This is a multi-line comment
   spanning multiple lines
 */
 ```
 While Nestor supports multi-line strings using triple quotes (""" or '''), they should not be used as comments. Instead, they should only be used for representing multi-line string values.

 **Naming Conventions**: Nestor enforces the following naming conventions, which are based on Python's naming conventions:

**Variables, functions, and instances**: Use lowercase words separated by underscores (e.g., my_variable, my_function).
**Constants**: Use uppercase words separated by underscores (e.g., MY_CONSTANT).
**Struct and rule-based function dispatchers**: Use CamelCase (e.g., MyClass, MyDispatcher).
**Modules and packages**: Use lowercase words separated by underscores (e.g., my_module, my_package).

Adhering to these conventions will ensure that Nestor code is consistent and easy to read across different projects and teams.

**Identifiers**: Identifiers in Nestor can include letters, digits, and underscores, but must not start with a digit. Identifiers are case-sensitive.

**Keywords**: Nestor has a set of reserved keywords that cannot be used as identifiers. 

### Expressions and Statements
Nestor supports a variety of expressions and statements for performing computations, defining variables and functions, and controlling the flow of execution. These constructs will be covered in more detail in subsequent sections of the documentation.

## Data Types
Nestor provides a rich set of built-in data types, designed to cover a wide range of use cases and facilitate efficient, expressive, and safe programming.

### Immutability and Mutability
In Nestor, all data types are immutable by default. This means that once a value has been assigned to a variable, the value cannot be changed. Immutability promotes safe and predictable code by preventing unintended modifications to data.

To create a mutable variable, use the mut keyword:

```python
x = 10          # immutable, int inferred
mut y = 11      # mutable, int inferred
```
Immutable variables must be initialized at the time of declaration, while mutable variables can be initialized later. All types have a default value (e.g., 0 for integers, empty list for lists).

### Basic Data Types
Nestor supports a variety of basic data types, including:

**Integers**: Nestor provides custom integer types, allowing users to specify the bit length and signed/unsigned properties. The default int type is unlimited, like in Python.

```python
i: int = 10               # unlimited integer
j: int8 = 5               # 8-bit integer
k: uint16 = 20            # 16-bit unsigned integer
l = 30                    # int inferred
```

**Floating-point numbers**: Nestor supports float and double types for representing real numbers with varying levels of precision.

```python
f: float = 3.14           # single-precision floating-point number
d: double = 3.1415926535  # double-precision floating-point number
d1 = 3.1415926535         # double inferred
```	
**Binary numbers**: Nestor provides the bin type for representing binary numbers.

```python
b: bin = 0b1010           # binary number
```
This will let you do built in operations on binary numbers, such as:

```python
b1 = 0b1010
b2 = 0b1100
b3 = b1 & b2 # 0b1000
b4 = b1.and(b2) # 0b1000
```

**Bytes**: Nestor provides the byte type for representing sequences of bytes.

```python
b: byte = b'Hello, Nestor!' # byte literal
```

The byte type can also be used in conjunction with the bin type to represent binary data.

```python
b1: bin = 0b1010
b2: bin = 0b1100
b3: byte = b1.concat(b2) # b'\x0a\x0c'
```


**Booleans**: Nestor supports the bool type for representing `true` and `false` values.

```python
b: bool = true
c = false # bool inferred
```

**Strings**: Nestor provides the str type for representing sequences of characters.

```python
s1: str = "Hello, Nestor!" # string literal with double quotes
s2 = 'Hello, Nestor!'      # string literal with single quotes, string inferred
```
Common string operations include:

```python
s1 = "Hello, Nestor!"
s2 = s1 + " How are you?" # "Hello, Nestor! How are you?"
s3 = ''.join([s1, s2])    # "Hello, Nestor!Hello, Nestor! How are you?"
s4 = s1[0:5]              # "Hello"
s5 = s1[7:]               # "Nestor!"
s6 = s1[-1]               # "!"
s7 = s1[0:5] + s1[7:]     # "HelloNestor!"
```
Nestor also supports multi-line strings using triple quotes (""" or ''').

```python
s1 = """This is a multi-line string
spanning multiple lines"""

s2 = '''This is also a multi-line string
spanning multiple lines'''
```
String interpolation is supported using f-strings.

```python
name = "Nestor"
s1 = f"Hello, {name}!" # "Hello, Nestor!"
```
Common string methods include:

```python
s1 = "Hello, Nestor!"
s2 = s1.upper() # "HELLO, NESTOR!"
s3 = s1.lower() # "hello, nestor!"
s4 = s1.count("l") # 2
s5 = s1.find("Nestor") # 7
s6 = s1.replace("Nestor", "World") # "Hello, World!"
```

**Regular expressions**: Nestor provides the regex type for representing regular expressions.

```python
r1: regex = r"^[a-z]+$" # regex literal that matches strings containing only lowercase letters
text = "Hello, Nestor!"
if r1.match(text):
    print("Match!")
else:
    print("No match!")

r2 regex = regex.compile(r"^[!.,:;]+$") # regex object that matches strings containing only punctuation
result = text.split(r2) # ["Hello", " Nestor"] immutable list of str inferred
```

**Bytes**: Nestor provides the byte type for representing sequences of bytes.

```python
b1: byte = 0x01           # byte literal
b2 = 0x02                 # byte inferred
```

**None**: Nestor provides the None type for representing the absence of a value.

```python
n: None = None
```

To check if a variable is None, use the is operator.

```python
n = None
if n is None:
    print("n is None")
```

### Compound Data Types

**Lists**: Nestor supports lists, which can be immutable or mutable. The list type is represented using square brackets and the element type (e.g., [int] for a list of integers).

```python
values1 = [1, 2, 3]              # immutable list of int, inferred
mut values2 = [1, 2, 3]          # mutable list of int, inferred
values3: [int] = [4, 5, 6]       # immutable list of int, explicit type
mut values4: [int] = [7, 8, 9]   # mutable list of int, explicit type
```	
Common list operations include:

```python
mut values = [1, 2, 3]
values.append(4)      # [1, 2, 3, 4]
values.extend([5, 6]) # [1, 2, 3, 4, 5, 6]
values.insert(0, 0)   # [0, 1, 2, 3, 4, 5, 6]
values.remove(3)      # [0, 1, 2, 4, 5, 6]
values.append(2)      # [0, 1, 2, 4, 5, 6, 2]
values.remove_all(2)  # [0, 1, 4, 5, 6]
values.pop()          # [0, 1, 4, 5]
values.pop(1)         # [0, 4, 5]
values.reverse()      # [5, 4, 0]
values.sort()         # [0, 4, 5]
values.sort(reverse=true) # [5, 4, 0]
values.clear()        # []
```

**Immutable Lists**: In Nestor, immutable lists are represented using the list type. An immutable list is essentaily a immutable fixed-length array. Nestor provides the list type for representing immutable lists.

```python
values: [int] = [1, 2, 3] # immutable list of int, explicit type
values[0] = 4 # error: cannot assign to immutable list
values.append(4) # error: cannot assign to immutable list
values2 = values + [4, 5, 6] # immutable list of int, inferred
print(values2) # [1, 2, 3, 4, 5, 6]
print(values[0]) # 1
print(values[1:]) # [2, 3]
print(values[-1]) # 3
print(values[0:2]) # [1, 2]
print(values[0:2] + values[2:]) # [1, 2, 3]
```
We can declare an immutable list of a fixed length using the list type.

```python
values: [int; 3] = [1, 2, 3] # immutable list of int, explicit type
```	
**Lists of mixed types**: Nestor supports lists of mixed types.

```python
values: [any] = [1, 2, 3, "Hello", true, 4.5] # immutable list of any, explicit type
values2 [int, str] = [1, "Hello"] # immutable list of int or str, explicit type
values3 [int, str, bool] = [1, "Hello", true] # immutable list of int, str, or bool, explicit type
```
The order of the types in the list type is important. The following example will not compile.

```python
values: [int, str] = ["Hello", 1] # error: cannot assign list of str or int to list of int or str
```

The any type is a special type that can be used to represent a list of mixed types.

```python
values: [any] = [1, 2, 3, "Hello", true, 4.5] # immutable list of any, explicit type
x = values[0] # int inferred
y:any = values[1] # any inferred
```

**Sets**: Nestor supports sets, which can be immutable or mutable. The set type is represented using curly braces and the element type (e.g., {int} for a set of integers).

```python
values1 = {1, 2, 3}              # immutable set of int, inferred
mut values2 = {1, 2, 3}          # mutable set of int, inferred
values3: {int} = {4, 5, 6}       # immutable set of int, explicit type
```
Common set operations include:

```python
mut values = {1, 2, 3}
values.add(4)                              # {1, 2, 3, 4}
values.update([5, 6])                      # {1, 2, 3, 4, 5, 6}
values.remove(3)                           # {1, 2, 4, 5, 6}
values.discard(2)                          # {1, 4, 5, 6}
values.intersect({4, 5, 6, 7})             # {4, 5, 6}
values.union({4, 5, 6, 7})                 # {1, 4, 5, 6, 7}
values.difference({4, 5, 6, 7})            # {1}
values.symmetric_difference({4, 5, 6, 7})  # {1, 7}
values.clear()                             # {}
```


**Maps**: Nestor supports maps, which can be immutable or mutable. The map type is represented using curly braces and the key and value types (e.g., {int: str} for a map of integers to strings).

```python
values1 = {1: "one", 2: "two", 3: "three"}              # immutable map of int to str, inferred
mut values2 = {1: "one", 2: "two", 3: "three"}          # mutable map of int to str, inferred
values3: {int: str} = {4: "four", 5: "five", 6: "six"}  # immutable map of int to str, explicit type
```
**Structs**: Nestor supports structs, which are user-defined types that can be used to group related data. Structs can be immutable or mutable.

```python
struct Point {
    x: int
    y: int
}

p1 = Point { x: 3, y: 4 }             # immutable struct, inferred
mut p2 = Point { x: 3, y: 4 }         # mutable struct, inferred
p3: Point = Point { x: 3, y: 4 }      # immutable struct, explicit type
```

**Class-like Structs**: Nestor supports class-like structs, which are user-defined types that can be used to group related data, and also methods, inheritance, interfaces, and polymorphism. They can also have one or more constructors, and a destructor. Class-like structs can be immutable or mutable.

```python
struct Point:
    x: int
    y: int

    constructor(x: int, y: int):
        this.x = x
        this.y = y

    constructor(x: int):
        this.x = x
        this.y = 0

    destructor():
        print("Point destroyed")    

    float distance():
        return sqrt(x ** 2 + y ** 2)
```

Inheritance:

```python
struct Point3D(Point):
    z: int

    constructor(x: int, y: int, z: int):
        super(x, y)
        this.z = z

    constructor(x: int, y: int):
        super(x, y)
        this.z = 0

    constructor(x: int):
        super(x)
        this.z = 0

    destructor():
        print("Point3D destroyed")

    float distance():
        return sqrt(x ** 2 + y ** 2 + z ** 2)
```

Interfaces:

```python
interface Shape:
    float area()
    float perimeter()

struct Rectangle(Shape):
    width: int
    height: int

    constructor(width: int, height: int):
        this.width = width
        this.height = height

    float area():
        return width * height

    float perimeter():
        return 2 * (width + height)
```

Polymorphism:

```python
struct Circle(Shape):
    radius: int

    constructor(radius: int):
        this.radius = radius

    float area():
        return pi * radius ** 2

    float perimeter():
        return 2 * pi * radius

struct Triangle(Shape):
    a: int
    b: int
    c: int

    constructor(a: int, b: int, c: int):
        this.a = a
        this.b = b
        this.c = c

    float area():
        s = (a + b + c) / 2
        return sqrt(s * (s - a) * (s - b) * (s - c))

    float perimeter():
        return a + b + c
```

#### Private and Protected Members
Properties and methods can be declared as private or protected. Private members can only be accessed within the same struct, while protected members can be accessed within the same struct and its subclasses.

To make a member private, prefix its name with an underscore (_). To make a member protected, prefix its name with two underscores (__).

```python
struct Point:
    x: int
    y: int

    constructor(x: int, y: int):
        this.x = x
        this.y = y

    float distance():
        return sqrt(x ** 2 + y ** 2)

    float _distance(): # private
        return sqrt(x ** 2 + y ** 2)

    float __distance(): # protected
        return sqrt(x ** 2 + y ** 2)
```

```python
struct Point:
    _x: int
    _y: int

    constructor(x: int, y: int):
        this._x = x
        this._y = y

    float distance():
        return sqrt(_x ** 2 + _y ** 2)

struct Point3D(Point):
    _z: int

    constructor(x: int, y: int, z: int):
        super(x, y)
        this._z = z

    float distance():
        return sqrt(_x ** 2 + _y ** 2 + _z ** 2)
```

#### Static Members
Properties and methods can be declared as static. Static members can be accessed without creating an instance of the struct.

To make a member static, prefix its name with the keyword static.

```python
struct Point:
    static x: int
    static y: int

    constructor(x: int, y: int):
        Point.x = x
        Point.y = y

    static float distance():
        return sqrt(Point.x ** 2 + Point.y ** 2)
```

#### Abstract Structs
Structs can be declared as abstract. Abstract structs cannot be instantiated, but can be inherited from.

To make a struct abstract, prefix its name with the keyword abstract.

```python
abstract struct Shape:
    float area()
    float perimeter()

struct Rectangle(Shape):
    width: int
    height: int

    constructor(width: int, height: int):
        this.width = width
        this.height = height

    float area():
        return width * height

    float perimeter():
        return 2 * (width + height)
```

#### Struct Methods (class methods in other languages)
Structs can have methods, which are functions that are defined within the struct. Struct methods can be static or non-static. Static struct methods can be accessed without creating an instance of the struct, while non-static struct methods can only be accessed by creating an instance of the struct.

```python
struct Point:
    x: int
    y: int

    constructor(x: int, y: int):
        this.x = x
        this.y = y

    float distance():
        return sqrt(x ** 2 + y ** 2)

    static float distance(x: int, y: int):
        return sqrt(x ** 2 + y ** 2)
```

### Enums
Enums are used to define a set of named constants. The enum keyword is used to declare an enum.

```python
enum Color:
    RED
    GREEN
    BLUE
```

Enums can also be declared with explicit values:

```python
enum Color:
    RED = 1
    GREEN = 2
    BLUE = 3
```

Enums can also be declared with a type:

```python
enum Color: int:
    RED = 1
    GREEN = 2
    BLUE = 3
```

Enums can be used as types:

```python
c: Color = Color.RED
```

### Other Types

**email**: The email type is used to store email addresses. The email type is a subtype of the string type, and can be used anywhere a string is expected. The email type provides built-in validation and utility functions.

```python
e1: email = "john@email.com"
print(e1.is_valid()) # True

e2: email = "john"
print(e2.is_valid()) # False
```

**password**: The password type is used to store passwords. The password type is a subtype of the string type, and can be used anywhere a string is expected. The password type provides built-in validation and utility functions.

```python
passw: password = "s3cr3t"
hashed = passw.hash() # hash the password
print(passw.validate(hashed)) # True
```

Passwords can also be validated against a list of common passwords:

```python
passw: password = "password"
print(passw.is_common()) # True
```

When declaring a password a regex can be provided to validate the password:

```python
# Defines a rule that the password must be at least 8 characters long and contain at least one number, one uppercase letter, and one lowercase letter.
passw: password(regex_rule='^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)[a-zA-Z\d]{8,}$')
passw = "s3cr3t" # raises an error
if Error:
    print(Error.handle())
```
**date**: The date type is used to store dates. The date type is a subtype of the string type, and can be used anywhere a string is expected. The date type provides built-in validation and utility functions.

```python
d1: date = "2023-04-03"
print(d1.is_valid()) # True
print(d1.is_leap_year()) # False
print(d1.is_weekend()) # False
print(d1.is_weekday()) # True
print(d1.is_today()) # False
print(d1.is_future()) # True
print(d1.is_past()) # False
print(d1.format('MM/DD/YYYY')) # 04/03/2023
d2: date = "2023-04-07"
print(d1.days_between(d2)) # 4
```	

**time**: The time type is used to store times. The time type is a subtype of the string type, and can be used anywhere a string is expected. The time type provides built-in validation and utility functions.

```python
t1: time = "12:00:00"
print(t1.is_valid()) # True
print(t1.is_am()) # False
print(t1.is_pm()) # True
print(t1.is_midnight()) # False
print(t1.is_noon()) # True
t2: time = "00:15:00"
print(t1.hours_between(t2)) # 12
print(t1.minutes_between(t2)) # 705
```

**geo**: The geo type is used to store geographic coordinates. The geo type is a subtype of the tuple type, and can be used anywhere a tuple is expected. The geo type provides built-in validation and utility functions.

```python
g1: geo = (38.8951100, -77.036370)
print(g1.is_valid()) # True
print(g1.latitude()) # 38.8951100
print(g1.longitude()) # -77.036370
# Distance between Washington DC and New York City
g2: geo = (40.7127753, -74.0059728)
print(g1.distance_between(g2)) # We get the distance in kilometers, but we can also get the distance in miles by passing the argument 'miles'
print(g1.distance_between(g2, 'miles')) # 225.0
```

## Variables and Constants
In Nestor, variables and constants are used to store and manipulate data throughout the program. This section covers the declaration, initialization, and assignment of variables and constants, as well as their respective naming conventions.

Variable Declaration and Initialization
Variables in Nestor can be declared with or without an explicit type. When the type is omitted, the compiler infers the type based on the value assigned to the variable.

To declare and initialize a variable, use the assignment operator (=):

```python
x = 10         # int inferred
y: int = 20    # explicit int type
```

By default, all variables are immutable, which means their values cannot be changed once assigned. To declare a mutable variable, use the mut keyword:

```python
x = 10          # immutable, int inferred
mut y = 11      # mutable, int inferred
```

Mutable variables can be assigned new values, while attempting to modify an immutable variable will result in a compilation error:

```python
x = 20          # compilation error, x is immutable
y = 21          # allowed, y is mutable
```

### Constants
Constants are used to represent values that should not change throughout the program's execution. In Nestor, constants are declared using the same syntax as variables, but with an uppercase naming convention:

```python
PI = 3.141592653589793
```

Constants must be initialized at the time of declaration and cannot be modified afterwards. Attempting to change the value of a constant will result in a compilation error:

```python
PI = 3.14       # compilation error, cannot modify a constant
```
## Operators
Nestor supports a variety of operators for performing computations and manipulating data. This section covers the various operators available in Nestor, including arithmetic, comparison, logical, and assignment operators.

### Arithmetic Operators
Nestor supports the following arithmetic operators:
 - **Addition (+)**, which adds two numbers together
 - **Subtraction (-)**, which subtracts one number from another
 - **Multiplication (\*)**, which multiplies two numbers together
 - **Exponentiation (\*\*)**, which raises one number to the power of another
 - **Division (/)**, which divides one number by another
 - **Integer Division (//)**, which divides one number by another and returns the integer result
 - **Modulus (%)**, which returns the remainder of one number divided by another

```python
x = 10
y = 3
z = x + y       # 13
z = x - y       # 7
z = x * y       # 30
z = x ** y      # 1000
z = x / y       # 3.3333333333333335
z = x // y      # 3
z = x % y       # 1
```
### Comparison Operators
Nestor supports the following comparison operators:
 - **Equal (==)**, which returns true if two values are equal
 - **Not Equal (!=)**, which returns true if two values are not equal
 - **Greater Than (>)**, which returns true if the first value is greater than the second
 - **Greater Than or Equal (>=)**, which returns true if the first value is greater than or equal to the second
 - **Less Than (<)**, which returns true if the first value is less than the second
 - **Less Than or Equal (<=)**, which returns true if the first value is less than or equal to the second

```python   
x = 10
y = 3
z = x == y      # false
z = x != y      # true
z = x > y       # true
z = x >= y      # true
z = x < y       # false
z = x <= y      # false
```
### Logical Operators
Nestor supports the following logical operators:
 - **And (and)**, which returns true if both values are true
 - **Or (or)**, which returns true if either value is true
 - **Not (not)**, which returns the opposite of the value

```python
x = true
y = false
z = x and y     # false
z = x or y      # true
z = not x       # false
```

### Assignment Operators
Nestor supports the following assignment operators:
 - **Assignment (=)**, which assigns a value to a variable
 - **Addition Assignment (+=)**, which adds a value to a variable and assigns the result
 - **Subtraction Assignment (-=)**, which subtracts a value from a variable and assigns the result
 - **Multiplication Assignment (\*=)**, which multiplies a variable by a value and assigns the result
 - **Exponentiation Assignment (\*\*=)**, which raises a variable to the power of a value and assigns the result
 - **Division Assignment (/=)**, which divides a variable by a value and assigns the result
 - **Integer Division Assignment (//=)**, which divides a variable by a value and assigns the integer result
 - **Modulus Assignment (%=)**, which divides a variable by a value and assigns the remainder

```python
x = 10
x += 3          # 13
x -= 3          # 10
x *= 3          # 30
x **= 3         # 1000
x /= 3          # 3.3333333333333335
x //= 3         # 3
x %= 3          # 1
```

## Unary Operators
Nestor supports the following unary operators:
 - **Positive (+)**, which returns the value unchanged
 - **Negative (-)**, which returns the value with the opposite sign
 - **Not (not)**, which returns the opposite of the value
 - **Pre-Increment (++x)**, which increments the value by 1 and returns the result
 - **Post-Increment (x++)**, which returns the value and then increments it by 1
 - **Pre-Decrement (--x)**, which decrements the value by 1 and returns the result
 - **Post-Decrement (x--)**, which returns the value and then decrements it by 1
```python
x = 10
y = +x          # 10
y = -x          # -10
y = not x       # false
y = ++x         # 11
y = x++         # 11
y = --x         # 10
y = x--         # 10
```

## Bitwise Operators
Nestor supports the following bitwise operators:
 - **Bitwise And (&)**, which performs a bitwise and operation on two numbers
 - **Bitwise Or (|)**, which performs a bitwise or operation on two numbers
 - **Bitwise Xor (^)**, which performs a bitwise xor operation on two numbers
 - **Bitwise Not (~)**, which performs a bitwise not operation on a number
 - **Bitwise Left Shift (<<)**, which performs a bitwise left shift operation on a number
 - **Bitwise Right Shift (>>)**, which performs a bitwise right shift operation on a number
 - **Bitwise Rotate Left (<<<)**, which performs a bitwise rotate left operation on a number
 - **Bitwise Rotate Right (>>>)**, which performs a bitwise rotate right operation on a number

```python
x = 0b1010      # Infered as type bin
y = 0b1100      # Infered as type bin
z = x & y       # 0b1000
z = x | y       # 0b1110
z = x ^ y       # 0b0110
z = ~x          # 0b0101
z = x << 1      # 0b10100
z = x >> 1      # 0b0101
z = x <<< 1     # 0b0101
z = x >>> 1     # 0b0101
```

## Range Operator
Nestor supports the following range operators:
 - **Range (...)**, which returns a range from the first value to the second value
 - **Range Inclusive (...=)**, which returns a range from the first value to the second value, inclusive
 - **Range Exclusive (...<)**, which returns a range from the first value to the second value, exclusive

These operators are used to create ranges, which are used in for loops and conditions where a sequence of values is needed. For example:
```python
loop i in 0...10:
    print(i)

```

```python
loop i in 0...=10:
    print(i)

```

```python
loop i in 0...<10:
    print(i)

```

```python
if x in 0...10:
    print("x is between 0 and 10")

```

```python
if x in 0...=10:
    print("x is between 0 and 10, inclusive")

```

```python
if x in 0...<10:
    print("x is between 0 and 10, exclusive")

```

### Extending Nestor Operators with the Operator Plugin System
Instead of having operator overloading, Nestor uses a plugin system to extend the functionality of operators. This allows you to extend the functionality of operators without having to modify the core language. For example, you can create a plugin that adds the `+` operator to the `str` type, allowing you to concatenate strings together:

```python
str str_add_plugin(left: str, right: str):
    return left.concat(right)

operator_append + (str_add_plugin, str, str)
```

### Memory Management and References
Nestor uses a memory management system similar to Python, where all variables reference a memory location. This means that when you assign a variable to another variable, both will reference the same memory location:

```python
x = [1, 2, 3]   # immutable list, int inferred
y = x           # y references the same list as x
```

Since all types are immutable by default, this reference behavior is safe and does not cause unexpected side effects. However, when working with mutable data structures, it's important to be aware of this behavior to avoid unintended modifications:

```python
mut x = [1, 2, 3]   # mutable list, int inferred
mut y = x           # y references the same list as x
y.append(4)         # x and y now reference the list [1, 2, 3, 4]
```

## Control Flow
Control flow statements in Nestor allow you to manage the execution of your program. This section covers the various control flow constructs available in Nestor, including conditional statements, loop constructs, and flow control keywords.

### Conditional Statements
Nestor provides if, else, and elif keywords for conditional statements, allowing you to execute different code blocks based on specific conditions.

```python
if condition1:
    # code block executed if condition1 is true
elif condition2:
    # code block executed if condition1 is false and condition2 is true
else:
    # code block executed if both condition1 and condition2 are false
```	

### Loop Constructs
Nestor introduces a unified loop keyword that replaces traditional for, while, and foreach constructs found in other programming languages. This simplifies the syntax and allows for more readable code. Here are a few examples of how the loop keyword can be used:

```python
loop:  # infinite loop
    # code block

loop i = 10:  # equivalent to "for i in range(10)"
    # code block, i iterates from 0 to 9

loop i = (1, 10, 2):  # equivalent to "for i in range(1, 10, 2)"
    # code block, i iterates from 1 to 9 by 2

loop i = (10, 1, -2):  # equivalent to "for i in range(10, 1, -2)"
    # code block, i iterates from 10 to 3 by -2

loop i = values.len(), value in values:  # equivalent to "for i, value in enumerate(values)"
    # code block, iterating through each value and its index

loop value in values:  # equivalent to "for value in values"
    # code block, iterating through each value in the list

loop i, value in values:  # equivalent to "for i, value in enumerate(values)"
    # code block, iterating through each value and its index

loop x < 10:  # equivalent to "while x < 10"
    # code block, executed while x is less than 10

do:  # equivalent to "do while"
    # code block, executed at least once
loop x < 10
```

### Nested Loops
Nestor supports nested loops using the following syntax:

```python
loop level1 i = 10, level2 j = 5:
    # code block, executed for each combination of i and j
    if i == 5:
        break level1
    if j == 3:
        continue level2
```
From the innermost loop, you can break out of all loops or any specific level using the break keyword followed by the loop label.

You can still do nested loops the traditional way, either with labels or not:
    
```python
loop i = 10:
    loop j = 5:
        # code block, executed for each combination of i and j
        if i == 5:
            break i
        if j == 3:
            continue j
```
    
```python
loop level1 i = 10:
    loop level2 j = 5:
        # code block, executed for each combination of i and j
        if i == 5:
            break level1
        if j == 3:
            continue level2
```

### Flow Control Keywords
Nestor provides several keywords for controlling the flow of execution within loops:

- **break**: Terminates the loop and continues executing the code after the loop.
- **continue**: Skips the rest of the current iteration and starts the next iteration of the loop.
- **recur**: Makes a recursive call to the current function, useful in anonymous functions.

These keywords can be used in conjunction with the loop construct to control the flow of your program based on specific conditions.

## Functions
Functions in Nestor are reusable pieces of code that can be called with arguments and can return values. This section covers the declaration and invocation of functions, including syntax, arguments, return values, lambdas, and closures.

### Function Declaration
Functions in Nestor are declared using the following syntax:

```python
return_type function_name(arg1: type, arg2: type = default):
    # function body
```

For functions that do not return a value, use the void type:

```python
void function_name(arg1: type, arg2: type):
    # function body
```

### Arguments
Nestor functions support positional arguments, default values, and keyword arguments, similar to Python. Type inference is also supported, which means that types for arguments can be omitted to create generic functions:

```python
function_name(arg1, arg2 = default):
    # function body, types inferred
```
Arguments can be declared as mutable using the mut keyword. When using mutable arguments, default values are not allowed:

```python
return_type function_name(arg1: type, mut arg2: type):
    # function body
```

### Return Values
Functions in Nestor can return multiple values. To specify the return types, use parentheses before the function name:

```python
(return_type1, return_type2) function_name(arg1: type, arg2: type):
    # function body
    return value1, value2
```

### Lambdas
Nestor supports lambda expressions, which are anonymous functions that can be assigned to variables or passed as arguments to other functions. Lambdas in Nestor are multi-statement and can use a capture clause like in C++.

Lambda syntax:

```python
[capture](arg1: type, arg2: type) -> return_type {
    # lambda body
}
```	
If the lambda body contains only one statement, curly braces ({}) can be omitted:

```python
[capture](arg1: type, arg2: type) -> return_type: single_statement
```

### Functions and capture clauses
Functions in Nestor can be passed as arguments to other functions. When a function is passed as an argument, it can be called from within the function body. If the function is declared with a capture clause, the captured variables can be accessed from within the function body.

```python
int adder [x](arg1: type, arg2: type):
    # function body, can access x
```

### Closures
Lambdas in Nestor can capture variables from their surrounding scope, creating closures. When a lambda captures a variable, it stores a reference to the variable, allowing the lambda to access and modify its value even after the original scope has exited.

## Concurrency and Parallelism
Nestor supports concurrency and parallelism through the use of agents. Agents are lightweight, concurrent entities that run independently and can communicate with each other. This section covers the creation and management of agents, as well as their communication mechanisms.

### Creating Agents
To create a new agent, use the run keyword followed by the name of the function or lambda expression you wish to execute concurrently:

```python
run function_name(args)  # starts a new agent running the function in parallel
```
For lambda expressions, the syntax would be:

```python
run [capture](arg1: type, arg2: type) -> return_type {
    # lambda body
}(args)
```	

Agents are scheduled and managed by the Nestor runtime, allowing for efficient execution on multi-core processors.

### Communicating Between Agents
Nestor provides mechanisms for communication and synchronization between agents. These mechanisms help to ensure safe and efficient concurrent operation. Some possible options for communication and synchronization include:

 - **Channels**: Queue-like data structures that allow agents to send and receive data in a thread-safe manner.
 - **Mutexes**: Objects that provide exclusive access to a shared resource.
 - **Semaphores**: Objects that control access to a shared resource by multiple agents using a counter.
 - **Atomic variables**: Variables that can be read and modified safely by multiple agents without the need for locking mechanisms.

You can choose the most suitable mechanisms based on your requirements and design goals.

#### Example of using channels, mutexes, and semaphores

```python
# agent 1
channel ch1
mutex m1
semaphore s1

run [ch1, m1, s1](arg1: type, arg2: type) -> return_type {
    # lambda body
}(args)

# agent 2
channel ch2
mutex m2
semaphore s2

run [ch2, m2, s2](arg1: type, arg2: type) -> return_type {
    # lambda body
}(args)
```

Here, agent 1 and agent 2 are communicating using channels, mutexes, and semaphores.

We can also use channels to communicate between agents:

```python
# agent 1
channel ch1

run [ch1](arg1: type, arg2: type) -> return_type {
    # lambda body
}(args)

# agent 2
channel ch2

run [ch1, ch2](arg1: type, arg2: type) -> return_type {
    # lambda body. Here we can use ch1 and ch2 and ch1 can be used to communicate with agent 1
}(args)
```

#### Using channels
Channels are queue-like data structures that allow agents to send and receive data in a thread-safe manner. They are created using the channel keyword:

```python
channel ch1

run [ch1](a: int, b: int) -> int {
    ch1.send(a + b) # send data to channel
    print('Agent 1 sent data to channel', a + b)
    return ch1.recv() # receive data from channel and return it
}(1, 2)

# agent 2

run [ch1](a: int, b: int) -> int {
    value: int = ch1.recv() # receive data from channel
    print('Agent 2 received data from channel', value)
    ch1.send(value + 1) # send data to channel
    print('Agent 2 sent data to channel', value + 1)
    return value + 1 # return value + 1
}(3, 4)
```
This example shows how agents can communicate using channels.
The output of this program is:

```python
Agent 1 sent data to channel 3
Agent 2 received data from channel 3
Agent 2 sent data to channel 4
```

#### Using mutexes
Mutexes are objects that provide exclusive access to a shared resource. They are created using the mutex keyword:

```python
mutex m1

run [m1](a: int, b: int) -> int {
    m1.lock() # lock the mutex
    print('Agent 1 locked the mutex')
    m1.unlock() # unlock the mutex
    print('Agent 1 unlocked the mutex')
    return a + b
}(1, 2)

# agent 2

run [m1](a: int, b: int) -> int {
    m1.lock() # lock the mutex
    print('Agent 2 locked the mutex')
    m1.unlock() # unlock the mutex
    print('Agent 2 unlocked the mutex')
    return a + b
}(3, 4)
```
This example shows how agents can communicate using mutexes.
The output of this program is:

```python
Agent 1 locked the mutex
Agent 1 unlocked the mutex
Agent 2 locked the mutex
Agent 2 unlocked the mutex
```

#### Handling deadlocks
Deadlocks can occur when two or more agents are waiting for each other to release a mutex. Nestor provides a mechanism to detect and handle deadlocks. When a deadlock is detected, the runtime will automatically unlock the mutexes and create an error object. The error object can be used to handle the deadlock.

```python
mutex m1
mutex m2

run [m1, m2](a: int, b: int) -> int {
    m1.lock() # lock the mutex
    print('Agent 1 locked the mutex')
    m2.lock() # lock the mutex
    print('Agent 1 locked the mutex')
    m1.unlock() # unlock the mutex
    print('Agent 1 unlocked the mutex')
    m2.unlock() # unlock the mutex
    print('Agent 1 unlocked the mutex')
    return a + b
}(1, 2)

# agent 2

run [m1, m2](a: int, b: int) -> int {
    m2.lock() # lock the mutex
    print('Agent 2 locked the mutex')
    m1.lock() # lock the mutex
    print('Agent 2 locked the mutex')
    m2.unlock() # unlock the mutex
    print('Agent 2 unlocked the mutex')
    m1.unlock() # unlock the mutex
    print('Agent 2 unlocked the mutex')
    return a + b
}(3, 4)

if error:
    print('Deadlock detected at mutex', error.mutex)
    # handle deadlock
    locked_mutexes = error.mutexes.locked
    for mutex in locked_mutexes:
        # unlock the mutex and set single_entry to 
        # true to only let a single agent enter the 
        # critical section at a time
        mutex.unlock(single_entry=true)  
        print('Mutex', mutex, 'unlocked')
```

The output of this program is:

```python
Agent 1 locked the mutex
Agent 1 locked the mutex
Agent 1 unlocked the mutex
Agent 1 unlocked the mutex
Agent 2 locked the mutex
Agent 2 locked the mutex
Deadlock detected at mutex m1
Mutex m1 unlocked
Mutex m2 unlocked
```

#### Using semaphores
Semaphores are objects that provide exclusive access to a shared resource. They are created using the semaphore keyword:

```python
semaphore s1

run [s1](a: int, b: int) -> int {
    s1.acquire() # acquire the semaphore
    print('Agent 1 acquired the semaphore')
    s1.release() # release the semaphore
    print('Agent 1 released the semaphore')
    return a + b
}(1, 2)

# agent 2

run [s1](a: int, b: int) -> int {
    s1.acquire() # acquire the semaphore
    print('Agent 2 acquired the semaphore')
    s1.release() # release the semaphore
    print('Agent 2 released the semaphore')
    return a + b
}(3, 4)
```
This example shows how agents can communicate using semaphores.
The output of this program is:

```python
Agent 1 acquired the semaphore
Agent 1 released the semaphore
Agent 2 acquired the semaphore
Agent 2 released the semaphore
```

#### Using events
Events are objects that provide exclusive access to a shared resource. They are created using the event keyword:

```python
event e1

run [e1](a: int, b: int) -> int {
    e1.wait() # wait for the event to be set
    print('Agent 1 waited for the event')
    e1.set() # set the event
    print('Agent 1 set the event')
    return a + b
}(1, 2)

# agent 2

run [e1](a: int, b: int) -> int {
    e1.wait() # wait for the event to be set
    print('Agent 2 waited for the event')
    e1.set() # set the event
    print('Agent 2 set the event')
    return a + b
}(3, 4)
```
This example shows how agents can communicate using events.
The output of this program is:

```python
Agent 1 waited for the event
Agent 1 set the event
Agent 2 waited for the event
Agent 2 set the event
```

#### Using barriers
Barriers are objects that provide exclusive access to a shared resource. They are created using the barrier keyword:

```python
barrier b1

run [b1](a: int, b: int) -> int {
    b1.wait() # wait for the barrier to be reached
    print('Agent 1 waited for the barrier')
    b1.reset() # reset the barrier
    print('Agent 1 reset the barrier')
    return a + b
}(1, 2)

# agent 2

run [b1](a: int, b: int) -> int {
    b1.wait() # wait for the barrier to be reached
    print('Agent 2 waited for the barrier')
    b1.reset() # reset the barrier
    print('Agent 2 reset the barrier')
    return a + b
}(3, 4)
```
This example shows how agents can communicate using barriers.
The output of this program is:

```python
Agent 1 waited for the barrier
Agent 1 reset the barrier
Agent 2 waited for the barrier
Agent 2 reset the barrier
```

#### Using queues
Queues are objects that provide exclusive access to a shared resource. They are created using the queue keyword:

```python
queue q1

run [q1](a: int, b: int) -> int {
    q1.put(1) # put an item in the queue
    print('Agent 1 put an item in the queue')
    q1.get() # get an item from the queue
    print('Agent 1 got an item from the queue')
    return a + b
}(1, 2)

# agent 2

run [q1](a: int, b: int) -> int {
    q1.put(1) # put an item in the queue
    print('Agent 2 put an item in the queue')
    q1.get() # get an item from the queue
    print('Agent 2 got an item from the queue')
    return a + b
}(3, 4)
```
This example shows how agents can communicate using queues.

The output of this program is:

```python
Agent 1 put an item in the queue
Agent 2 put an item in the queue
Agent 1 got an item from the queue
Agent 2 got an item from the queue
```



## Rule-based Function Dispatchers
Rule-based function dispatchers in Nestor provide a powerful mechanism to define and call functions based on specific conditions or criteria. They enable the creation of flexible, modular, and extensible code. This section covers the creation of rule-based function dispatchers, the definition of conditions, and the invocation of these dispatchers.

### Creating Rule-based Function Dispatchers
To create a rule-based function dispatcher, define a class-like structure and add methods with conditions specified using decorators. The conditions are evaluated during the invocation of the dispatcher.

Here's an example of a rule-based function dispatcher:

```python	
dispathcher MyDispatcher:
    @condition(arg1 > 10, arg2 == "hello")
    @condition(arg1 < 10, arg2 == "world")
    int function1(arg1: int, arg2: str):
        # function body

    @condition(arg1 > arg2)
    bool function2(arg1: float, arg2: float):
        # function body

    # Conditions can also be specified using lambda expressions
    @condition([] (arg1): arg1 % 2 == 0)
    int even_values_only(arg1: int):
        # function body
```

### Invoking Rule-based Function Dispatchers
To invoke a rule-based function dispatcher, create an instance of the dispatcher and call it with the necessary arguments. The dispatcher evaluates the conditions for each method, and if a condition is satisfied, it executes the corresponding method.

```python
example_dispatcher = MyDispatcher()

result = example_dispatcher(arg1, arg2)
```
The dispatcher returns a result object containing the return values from all the methods that were executed during the invocation.

This draft should serve as a starting point for the Rule-based Function Dispatchers section of your Nestor programming language documentation. Feel free to modify, expand, or reorganize the content as needed to fit your specific goals and requirements.

### Defining Conditions
Conditions are specified using the condition decorator. Conditions can be specified using lambda expressions or a conditional expression. The conditional expression is a simplified version of the Python conditional expression, and is used to specify conditions that involve multiple arguments.

```python
@condition(arg1 > 10, arg2 == "hello")
@condition(arg1 < 10, arg2 == "world")
```
The conditional expression is evaluated as follows:

```python
(arg1 > 10) and (arg2 == "hello") or (arg1 < 10) and (arg2 == "world")
```

### Order of Precedence in Rule-based Function Dispatchers
The order of precedence in rule-based function dispatchers is as follows:

 1. The order in which the methods are defined in the dispatcher class.
 2. The order in which the conditions are specified for each method.
 3. The order in which the arguments are specified in the conditional expression.

 ### Return Values
The return values from the methods that were executed during the invocation of the dispatcher are stored in a result object. The result object can be accessed using the value property. The result object also contains a list of the methods that were executed during the invocation.
    
```python
result = example_dispatcher(arg1, arg2)
loop method in result.methods:
    print(method.name)
    print(method.return_value)
```

## Error Handling
Nestor introduces a simplified and more expressive approach to error handling, using built-in error objects instead of exceptions. 

The motivation behind this approach is to provide a more flexible and modular way to handle errors. Instead of having a try-catch clause, you can perform a check in the caller code. This has the added benefit of allowing you to handle errors in a more granular way, by passing them down the call stack.

This section covers the creation and handling of error objects, as well as their propagation through the call stack.

### Creating Error Objects
Instead of raising an exception, create an instance of the built-in error object. This has the same effect as raising an exception but offers more flexibility:

```python
error.create_error("Error message")
```
You can also set an error handler function or lambda expression when creating an error object:

```python
error.create_error("Error message", [](): print("Handling the error"))
```

### Handling Error Objects
Error objects, if set, are automatically injected into the caller's scope. Instead of having a try-catch clause, you can perform a check in the caller code:

```python
if error:
    msg: str = error.handle()  # Calls the error handler if present, and returns the error message
```

### Changing the Error Handler
The error object can to handle multiple errors. To append a new error handler, use the create_error method:

```python
error.create_error("Error message", [](): print("Handling the error"))
```

To check all errors, use the errors property:

```python
loop err in error.errors:
    print(err.message)
    print(err.handle())
```

### Propagation of Unhandled Errors
Unhandled errors are passed down the call stack, similar to exceptions. If an error object is not handled in the current scope, it will be propagated to the previous scope until it is either handled or reaches the top level of the program, at which point the program will terminate with an appropriate error message.

## Memory Model
The memory model of Nestor is designed to provide a balance between performance and ease of use. It combines epoch-based garbage collection with built-in scoped regions to provide a flexible and efficient memory management solution. This section covers the language's memory management, including how memory is allocated, deallocated, and accessed.

### Epoch-based Garbage Collection
Epoch-based garbage collection divides the lifetime of the program into discrete time intervals called epochs. Each epoch has a separate memory pool, and all allocations during an epoch are made from that pool. When an epoch ends, its memory pool can be deallocated all at once, reducing memory fragmentation and improving efficiency, particularly for short-lived objects.

To use epoch-based garbage collection in Nestor, you can create an epoch using the with epoch() construct:

```python
with epoch():  # Creates a new epoch
    mut values: [int]  # Memory allocated within the current epoch
    x: int = 15  # Memory allocated within the current epoch
# End of the epoch; memory for values and x is deallocated
```	

### Scoped Regions
In addition to epochs, Nestor also supports built-in scoped regions, which are memory pools associated with a specific scope in the program. When the scope ends, all memory allocated within that region is deallocated. This allows for more fine-grained control over memory allocation and deallocation, particularly for objects with known lifetimes.

To use scoped regions in Nestor, you can create a scoped region using the with scoped_region() construct:

```python
with scoped_region() as region:  # Creates a new scoped region
    mut values: [int]  # Memory allocated within the current epoch
    x: int = 15  # Memory allocated within the current epoch
    some_function(region)  # Pass the scoped region to a function
# End of the scoped region; memory for values and x is deallocated
```	
Passing an instance of the scoped region to a function allows the function to allocate memory within the same region:

```python
void some_function(region): # region is inferred to be a scoped region
    new_list = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
```

When the scoped region is passed to a function, the memory allocated within the function is deallocated when the scope of the original scoped region ends, ensuring consistent memory management.

Remember that sharing scoped regions between threads or functions may introduce potential race conditions or other concurrency-related issues. Proper use of synchronization mechanisms and Nestor's strong concurrency features is essential to ensure data consistency and avoid such issues.

### Memory Allocation
Memory is allocated using the allocate function. The allocate function takes a type as an argument and returns a pointer to the allocated memory. The type can be a primitive type, a reference type, or a generic type. The allocate function can also be used to allocate memory for a mutable list or a mutable map.


This can be done in a scoped region or an epoch but not outside of any scope:

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
```

### Memory Deallocation
Memory is deallocated automatically when the scope of the scoped region or the epoch ends. However, you can also deallocate memory manually using the deallocate function. The deallocate function takes an instance of a region or an epoch as an argument and deallocates all memory allocated within that region or epoch.

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.deallocate()  # All memory allocated within the scoped region is deallocated
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    deallocate()  # All memory allocated within the current epoch is deallocated
```

You can also deallocate memory for a specific object using the deallocate function:

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.deallocate(x)  # Memory allocated for x is deallocated
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    deallocate(x)  # Memory allocated for x is deallocated
```

### Memory Access
Memory can be accessed using the dereference operator. The dereference operator takes a pointer as an argument and returns the value stored at that memory location. The dereference operator can also be used to access elements of a mutable list or a mutable map.

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    values[0] = 10  # Memory allocated for the first element of the mutable list is accessed
    *values[0] = 10  # Memory allocated for the first element of the mutable list is accessed
    x = 10  # Memory allocated for x is accessed
    *x = 10  # Memory allocated for x is accessed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    values[0] = 10  # Memory allocated for the first element of the mutable list is accessed
    *values[0] = 10  # Memory allocated for the first element of the mutable list is accessed
    x = 10  # Memory allocated for x is accessed
    *x = 10  # Memory allocated for x is accessed
```

### Memory Reclamation
Memory is reclaimed automatically when the scope of the scoped region or the epoch ends. However, you can also reclaim memory manually using the reclaim function. The reclaim function takes an instance of a region or an epoch as an argument and reclaims all memory allocated within that region or epoch.

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.reclaim()  # All memory allocated within the scoped region is reclaimed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    reclaim()  # All memory allocated within the current epoch is reclaimed
```

You can also reclaim memory for a specific object using the reclaim function:

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.reclaim(x)  # Memory allocated for x is reclaimed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    reclaim(x)  # Memory allocated for x is reclaimed
```

### Memory Reclamation with Garbage Collection
Memory is reclaimed automatically when the scope of the scoped region or the epoch ends. However, you can also reclaim memory manually using the garbage_collect function. The garbage_collect function takes an instance of a region or an epoch as an argument and reclaims all memory allocated within that region or epoch.

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.garbage_collect()  # All memory allocated within the scoped region is reclaimed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    garbage_collect()  # All memory allocated within the current epoch is reclaimed
```

You can also reclaim memory for a specific object using the garbage_collect function:

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    region.garbage_collect(x)  # Memory allocated for x is reclaimed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    garbage_collect(x)  # Memory allocated for x is reclaimed
```

### Memory Reclamation with Garbage Collection and Defer
Memory is reclaimed automatically when the scope of the scoped region or the epoch ends. However, you can also reclaim memory manually using the garbage_collect function. The garbage_collect function takes an instance of a region or an epoch as an argument and reclaims all memory allocated within that region or epoch.

```python
with scoped_region() as region:
    mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
    defer region.garbage_collect()  # All memory allocated within the scoped region is reclaimed
```

```python
with epoch():
    mut values: [int] = allocate(mut [int])  # Memory allocated for a mutable list within the current epoch, it will be deallocated when the current epoch ends
    x: int = allocate(int)  # Memory allocated for an integer within the current epoch, it will be deallocated when the current epoch ends
    defer garbage_collect()  # All memory allocated within the current epoch is reclaimed
```

### Best Practices
The best practices for memory management in the language are as follows:

  * Use the scoped region to allocate memory for a specific scope.
  * Use the epoch to allocate memory for a specific scope.
  * Use the defer statement to reclaim memory allocated within a scope.
  * Use the defer statement to reclaim memory allocated within a scope.

### Memory Management in the Standard Library
The standard library uses the scoped region to allocate memory for a specific scope. The standard library uses the defer statement to reclaim memory allocated within a scope.

### Memory Management in the Compiler
The compiler uses the scoped region to allocate memory for a specific scope. The compiler uses the defer statement to reclaim memory allocated within a scope.

### Memory Management in the Runtime
The runtime uses the scoped region to allocate memory for a specific scope. The runtime uses the defer statement to reclaim memory allocated within a scope.

### Memory Management and Concurrency
The memory management structures in Nestor are thread-safe. This means that you can use the scoped region, the epoch, and the defer statement in a concurrent environment.

It can also be used to define a memory management strategy for a concurrent environment. For example, you can use the scoped region to allocate memory for a specific scope and use the defer statement to reclaim memory allocated within a scope. This will let you execute agents in different scopes and reclaim memory allocated within those scopes when the threads end.

Example of running agents in different scopes and reclaiming memory allocated within those scopes when the threads end:

```python
void worker() {
    with scoped_region() as region:
        mut values: [int] = region.allocate(mut [int])  # Memory allocated for a mutable list within the passed scoped region, it will be deallocated when the scope of the scoped region ends
        x: int = region.allocate(int)  # Memory allocated for an integer within the passed scoped region, it will be deallocated when the scope of the scoped region ends
        defer region.reclaim()  # All memory allocated within the scoped region is reclaimed
        // Do something
    }
}

main:
    run worker() # Start a new agent and let it use the scoped region to allocate memory for a specific scope and use the defer statement to reclaim memory allocated within a scope
    run worker() # This agent will use a different scoped region to allocate memory for a specific scope and use the defer statement to reclaim memory allocated within a scope
```

## Status of the Nestor Project
The Nestor project is in the early stages of development.

Currently the language syntax and specification are being developed.

When that is done a reference implementation of the language will be developed as an interpreter. This so the syntax and specification can be tested.

After that a compiler will be developed..

At this stage a standard library will be developed.

### Contributing to the Nestor Project
Nestor is an open source project. You can contribute to the Nestor project by:

  * Reporting bugs
  * Suggesting new features
  * Writing code
  * Writing documentation
  * Writing tutorials
  * Writing blog posts
  * Spreading the word

For now, as we are in the early stages of development, the best way to contribute to the Nestor project is to contact the project lead.

### Contacting the Project Lead
You can contact the project lead by sending an email to:

nestor@arthead.se
