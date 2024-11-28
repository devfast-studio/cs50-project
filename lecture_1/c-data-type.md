I'll help you explain data types in C using clear code blocks and markdown formatting. Let me break this down into key sections:

# Basic Data Types in C

## Integers (int)

```c
// Integers - Whole numbers (4 bytes)
int age = 20;                // Regular integer (-2^31 to 2^31-1)
unsigned int count = 1000;   // Only positive integers (0 to 2^32-1)
```

## Characters (char)

```c
// Characters - Single characters (1 byte)
char grade = 'A';           // Single character
char digit = '7';           // Numeric character
```

## Floating Point Numbers

```c
// Floating point numbers (4 bytes)
float price = 10.99;        // Less precise decimal numbers
// Double precision numbers (8 bytes)
double pi = 3.14159265359;  // More precise decimal numbers
```

## Void Type

```c
// Void - Used for functions that don't return values
void printHello(void) {     // Takes no parameters
    printf("Hello!\n");     // Returns nothing
}
```

# CS50 Library Types

These require `#include <cs50.h>`

## Boolean (bool)

```c
// Boolean values - true or false
bool isStudent = true;
bool hasPassed = false;
```

## String

```c
// Strings - Collection of characters
string name = "Alice";
string message = "Hello, world!";
```

## Variable Declaration and Assignment

You can declare and assign variables in two ways:

```c
// Method 1: Separate declaration and assignment
int score;
score = 95;

// Method 2: Declaration with initialization
int score = 95;

// Multiple variables of the same type
int x = 1, y = 2, z = 3;
```

Key points to remember:

- Always declare variables before using them
- Don't redeclare variables - declare them once and then just assign new values
- Choose a data type that can appropriately store your data
- Initialize variables when you declare them unless you have a specific reason not to

Would you like me to clarify any part of this explanation?
