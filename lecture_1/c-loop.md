Based on the lecture materials, let me explain loops and text output in C with some clear examples.

In C, we can output text in patterns or loops using `printf` and different types of loops. Here are the key loop types and how to use them for text output:

1. While Loop:

```c
// Print "hello" 5 times
int i = 0;
while (i < 5) {
    printf("hello\n");
    i++;
}
```

2. Do-While Loop (runs at least once):

```c
// Print numbers from 1 to 5
int i = 1;
do {
    printf("%i\n", i);
    i++;
} while (i <= 5);
```

3. For Loop (when you know number of iterations):

```c
// Print "CS50" 3 times
for (int i = 0; i < 3; i++) {
    printf("CS50\n");
}
```

For nested patterns, you can use nested loops:

```c
// Print a square of # characters
int size = 3;
for (int i = 0; i < size; i++) {
    for (int j = 0; j < size; j++) {
        printf("#");
    }
    printf("\n");  // New line after each row
}
```

This would output:

```
###
###
###
```

Key things to remember:

- Use `\n` for newlines
- The `%i` format code is for integers
- `printf` doesn't automatically add newlines
- Loop counters typically start at 0 in C
- Check your loop conditions carefully to avoid infinite loops

Would you like to see more specific examples or patterns?
