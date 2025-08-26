---
tags:
  - ProgrammingLanguage
---

# C Programming Language Cheat Sheet
## Table of Contents
- [Basics](#basics)
- [Data Types](#data-types)
    -[Variable declaration](#variable-declaration)
- [Control Structures](#control-structures)
    - [If-Else](#if-else)
    - [Switch](#switch)
    - [Loops](#loops)
        - [For Loop](#for-loop)
        - [While Loop](#while-loop)
        - [Do-While Loop](#do-while-loop)
- [Functions](#functions)
- [Arrays](#arrays)
- [Pointers](#pointers)
- [Structures](#structures)
- [File I/O](#file-io)
    - [Reading a File](#reading-a-file)
    - [Writing to a File](#writing-to-a-file)
- [Common Functions](#common-functions)
- [Preprocessor Directives](#preprocessor-directives)
- [Memory Management](#memory-management)
- [Comments](#comments)

## Basics
```c
#include "stdio.h"

int main() {
    printf("Hello, World!\n");
    return 0;
}
```



## Data Types
- `int`: Integer
- `float`: Floating point number
- `double`: Double precision floating point number
- `char`: Character
- `void`: Empty



### Variable Declaration

```c
// Integers
int number = 10;

// Floating Point Numbers
float decimal = 3.14;

// Double Precision Floating Point Numbers
double bigDecimal = 3.14159265359;

// Characters
char letter = 'A';

// Strings
char string[] = "Hello, World!";

// Pointers
int *pointer;
```c
// Initializing arrays
int numbers[5] = {1, 2, 3, 4, 5};
char letters[5] = {'A', 'B', 'C', 'D', 'E'};
float decimals[3] = {1.1, 2.2, 3.3};

// Initializing arrays without specifying size
int moreNumbers[] = {6, 7, 8, 9, 10};
char moreLetters[] = "Hello";
```
```

## Control Structures
### If-Else
```c
if (condition) {
    // code
} else {
    // code
}
```

### Switch
```c
switch (variable) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code
}
```

### Loops
#### For Loop
```c
for (initialization; condition; increment) {
    // code
}
```

#### While Loop
```c
while (condition) {
    // code
}
```

#### Do-While Loop
```c
do {
    // code
} while (condition);
```

## Functions
```c
returnType functionName(parameters) {
    // code
    return value;
}
```

## Arrays
```c
dataType arrayName[arraySize];
```

## Pointers
```c
dataType *pointerName;
pointerName = &variable;
```

## Structures
```c
struct StructName {
    dataType member1;
    dataType member2;
    // more members
};
```

## File I/O
### Reading a File
```c
FILE *filePointer;
filePointer = fopen("filename", "r");
fscanf(filePointer, "%s", buffer);
fclose(filePointer);
```

### Writing to a File
```c
FILE *filePointer;
filePointer = fopen("filename", "w");
fprintf(filePointer, "data");
fclose(filePointer);
```

## Common Functions
- `printf()`: Print formatted output
- `scanf()`: Read formatted input
- `strlen()`: Get string length
- `strcpy()`: Copy string
- `strcat()`: Concatenate strings
- `strcmp()`: Compare strings

## Preprocessor Directives
- `#define`: Define a macro
- `#include`: Include a header file
- `#ifdef`: Conditional compilation

```c
#define PI 3.14
#include <stdio.h>

#ifdef DEBUG
    printf("Debug mode\n");
#endif
```

## Memory Management
- `malloc()`: Allocate memory
- `calloc()`: Allocate and zero-initialize memory
- `free()`: Deallocate memory

```c
int *ptr = (int*) malloc(sizeof(int) * n);
free(ptr);
```

## Comments
- Single line: `// comment`
- Multi-line: `/* comment */`
