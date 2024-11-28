# C Programming Guide for JavaScript Developers

## 1. Key Differences from JavaScript

### Variables and Types

- C requires explicit type declaration
- No `let` or `const` - use type names directly
- Must initialize variables before use
- No `undefined` or `null` - use 0 or NULL instead

```c
// JavaScript
let age = 25;

// C
int age = 25;
```

### Type System

Common types:

- `int`: whole numbers
- `char`: single characters
- `float`: decimal numbers
- `double`: larger decimal numbers
- `char*`: strings (pointer to characters)
- `void`: no type/return value

## 2. Memory Management

### Stack Memory (Automatic)

- Fixed size arrays
- Local variables
- Automatically managed

```c
int numbers[5] = {1, 2, 3, 4, 5};  // Stack allocation
char name[] = "John";               // Stack allocation
```

### Heap Memory (Manual)

- Dynamic allocation using malloc()
- Must free manually
- Persists until explicitly freed

```c
char* str = malloc(50);  // Allocates 50 bytes
free(str);               // Must free when done
```

### When to Use malloc()

Use malloc() when:

- Size needed is unknown at compile time
- Memory needs to persist beyond current function
- Creating dynamic data structures

Don't use malloc() when:

- Using fixed-size arrays
- Using string literals
- Using CS50's string type

### malloc() Sizing

```c
// For strings
char* str = malloc(50);                    // Space for 49 chars + null terminator

// For arrays
int* numbers = malloc(5 * sizeof(int));    // Space for 5 integers
double* prices = malloc(5 * sizeof(double)); // Space for 5 doubles

// For dynamic strings
char* message = malloc(strlen(source) + 1); // +1 for null terminator
```

## 3. Strings in C

### Different Ways to Handle Strings

```c
// Pure C
char* name1 = "John";     // String literal (read-only)
char name2[] = "John";    // Character array
char* name3 = malloc(50); // Dynamic allocation

// CS50
string name4 = "John";    // CS50's string type
```

### String Operations

```c
#include <string.h>

strlen(str);      // Get length
strcpy(dest, src); // Copy strings
strcat(dest, src); // Concatenate
strcmp(s1, s2);    // Compare strings
```

## 4. Input/Output

### Printf Format Specifiers

- `%d` or `%i`: integers
- `%f`: float/double
- `%c`: single character
- `%s`: string
- `%p`: pointer address

```c
printf("Number: %d, Name: %s\n", 42, "John");
```

### Getting Input

```c
// CS50 Library
string name = get_string("Enter name: ");
int age = get_int("Enter age: ");

// Standard C
char name[50];
scanf("%s", name);
```

## 5. Functions

### Function Declaration

#### Basic Syntax

```c
// Basic function structure
return_type function_name(parameter_type parameter_name) {
    // function body
    return value;
}

// Example
int add(int x, int y) {
    return x + y;
}
```

#### Function Prototypes

```c
// Prototype (in header file or top of program)
int add(int x, int y);
void printMessage(char* message);
double calculateArea(double radius);

// Parameter names are optional in prototypes
int add(int, int);         // Also valid
```

#### Project Organization

1. Single File Programs:

```c
// All in one .c file
int add(int x, int y);     // Prototype

int main(void) {
    int sum = add(5, 3);
    return 0;
}

int add(int x, int y) {    // Implementation
    return x + y;
}
```

2. Multiple File Programs:

```c
// math.h
#ifndef MATH_H
#define MATH_H

int add(int x, int y);
int subtract(int x, int y);

#endif

// math.c
#include "math.h"

int add(int x, int y) {
    return x + y;
}

int subtract(int x, int y) {
    return x - y;
}

// main.c
#include "math.h"

int main(void) {
    int result = add(5, 3);
    return 0;
}
```

#### Return Types

```c
// Void return - function doesn't return anything
void printNumber(int x) {
    printf("%d\n", x);
}

// Integer return
int getNumber(void) {
    return 42;
}

// String return (char pointer)
char* getMessage(void) {
    return "Hello";
}
```

#### Parameters

```c
// No parameters
void sayHello(void) {
    printf("Hello\n");
}

// Multiple parameters
int multiply(int x, int y, int z) {
    return x * y * z;
}

// Pointer parameters
void modifyString(char* str) {
    strcpy(str, "New text");
}
```

#### Key Differences from JavaScript

- Must declare return type
- Must declare parameter types
- No default parameters
- No rest parameters
- No arrow functions
- Functions can't be assigned to variables
- Must have prototype or definition before use

#### Best Practices

1. Use prototypes when:

   - Functions call each other mutually
   - Organizing code across multiple files
   - Main logic should appear at top

2. Header File Organization:

   - Put related function prototypes together
   - Use include guards
   - Keep implementation details in .c files

3. Naming Conventions:
   - Use descriptive function names
   - Use snake_case (C convention)
   - Group related functions with common prefixes

### Main Function

```c
int main(void) {
    // Program starts here
    return 0;
}
```

## 6. Best Practices

### Memory Management

- Always check malloc() return for NULL
- Free all allocated memory
- Use sizeof() for proper sizing

```c
char* str = malloc(50);
if (str == NULL) {
    // Handle error
    return 1;
}
// Use str
free(str);
```

### Program Structure

- Include necessary headers at top
- Define constants with #define
- Declare function prototypes
- Implement main function
- Implement other functions

### Debugging Tips

- Use printf for debugging
- Check return values
- Validate memory allocations
- Check for buffer overflows
- Use CS50's debug50 tool

Remember: C is much lower-level than JavaScript. You'll need to manage memory manually and be more explicit about types and operations. Start with small programs and gradually work up to more complex ones.
