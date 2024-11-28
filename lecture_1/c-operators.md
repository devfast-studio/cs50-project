I'll help explain operators in C based on the source material. Here are the key concepts:

### Arithmetic Operators

```c
// Basic arithmetic operators
+ // Addition
- // Subtraction
* // Multiplication
/ // Division
% // Modulus (remainder)

// Example:
int x = y + 1;    // Add 1 to y and store in x
x = x * 5;        // Multiply x by 5 and store result back in x
int m = 13 % 4;   // m gets value 1 (remainder when 13 divided by 4)
```

### Compound Assignment Operators

```c
// Shorter way to modify a variable
x += 5;   // Same as: x = x + 5
x -= 5;   // Same as: x = x - 5
x *= 5;   // Same as: x = x * 5
x /= 5;   // Same as: x = x / 5
x %= 5;   // Same as: x = x % 5

// Increment/Decrement
x++;      // Same as: x = x + 1
x--;      // Same as: x = x - 1
```

### Logical Operators

```c
// Used for boolean expressions - evaluate to true(1) or false(0)
&&    // AND - true if both operands are true
||    // OR - true if at least one operand is true
!     // NOT - inverts the value (also called bang)

// Examples:
if (x && y)    // True only if both x AND y are true
if (x || y)    // True if either x OR y (or both) are true
if (!x)        // True if x is false
```

### Relational Operators

```c
// Compare values
<     // Less than
<=    // Less than or equal to
>     // Greater than
>=    // Greater than or equal to
==    // Equal to (comparison)
!=    // Not equal to

// Examples:
if (x < y)     // True if x is less than y
if (x >= y)    // True if x is greater than or equal to y
if (x == y)    // True if x equals y (be careful not to use single =)
if (x != y)    // True if x is not equal to y
```

Important notes:

- In C, any non-zero value is considered true, while 0 is false
- Don't confuse = (assignment) with == (comparison)
- The logical operators && and || stop evaluating as soon as they can determine the result (short-circuit evaluation)
- The modulus operator % is especially useful for wrapping numbers into a range (like for random numbers) or checking if a number is even/odd
