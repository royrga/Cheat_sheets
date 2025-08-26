---
tags:
  - ProgrammingLanguage
---

# TypeScript Cheat Sheet
## Table of Contents
- [Basic Types](#basic-types)
- [Operators](#operators)
- [Interfaces](#interfaces)
- [Classes](#classes)
- [Functions](#functions)
- [Generics](#generics)
- [Enums](#enums)
- [Type Assertions](#type-assertions)
- [Modules](#modules)
- [Utility Types](#utility-types)

## Basic Types
```typescript
let isDone: boolean = false; // Boolean
let count: number = 42; // Number
let name: string = "TypeScript"; // String
let list: number[] = [1, 2, 3]; // Array of numbers
let tuple: [string, number] = ["hello", 10]; // Tuple (fixed-type array)
let notSure: any = 4; // Any (dynamic type, avoid using)
let nothing: void = undefined; // Void (no type, used for functions)
let u: undefined = undefined; // Undefined
let n: null = null; // Null
```

## Operators
TypeScript supports a variety of operators that can be used for performing operations on variables and values. These include arithmetic, comparison, logical, and more.

### Arithmetic Operators
```typescript
let sum = 5 + 3; // Addition
let difference = 5 - 3; // Subtraction
let product = 5 * 3; // Multiplication
let quotient = 5 / 3; // Division
let remainder = 5 % 3; // Modulus
let increment = ++sum; // Increment
let decrement = --difference; // Decrement
```

### Comparison Operators
```typescript
let isEqual = 5 == "5"; // Equality (loose)
let isStrictEqual = 5 === 5; // Strict equality
let isNotEqual = 5 != "5"; // Inequality (loose)
let isStrictNotEqual = 5 !== 5; // Strict inequality
let isGreater = 5 > 3; // Greater than
let isLess = 5 < 3; // Less than
let isGreaterOrEqual = 5 >= 3; // Greater than or equal to
let isLessOrEqual = 5 <= 3; // Less than or equal to
```

### Logical Operators
```typescript
let and = true && false; // Logical AND
let or = true || false; // Logical OR
let not = !true; // Logical NOT
```

### Bitwise Operators
```typescript
let andBitwise = 5 & 3; // AND
let orBitwise = 5 | 3; // OR
let xorBitwise = 5 ^ 3; // XOR
let notBitwise = ~5; // NOT
let leftShift = 5 << 1; // Left shift
let rightShift = 5 >> 1; // Right shift
let unsignedRightShift = 5 >>> 1; // Unsigned right shift
```

### Assignment Operators
```typescript
let x = 10;
x += 5; // Add and assign
x -= 5; // Subtract and assign
x *= 5; // Multiply and assign
x /= 5; // Divide and assign
x %= 5; // Modulus and assign
```

### Other Operators
- **Ternary Operator**: A shorthand for `if-else` statements.
    ```typescript
    let result = 5 > 3 ? "greater" : "lesser";
    ```
- **Optional Chaining (`?.`)**: Safely access deeply nested properties.
    ```typescript
    let value = obj?.property?.subProperty;
    ```
- **Nullish Coalescing (`??`)**: Provide a default value if the left operand is `null` or `undefined`.
    ```typescript
    let value = someVariable ?? "default";
    ```
- **Spread Operator (`...`)**: Expand arrays or objects.
    ```typescript
    let arr = [1, 2, 3];
    let newArr = [...arr, 4, 5];
    ```
- **Rest Operator (`...`)**: Collect arguments into an array.
    ```typescript
    function sum(...numbers: number[]) {
            return numbers.reduce((acc, curr) => acc + curr, 0);
    }
    ```

## Interfaces
### Interfaces
Interfaces in TypeScript are used to define the structure of an object. They act as a contract that specifies the properties and their types that an object must have. Interfaces are particularly useful for defining the shape of data, ensuring type safety, and enabling better code readability and maintainability.

#### When to Use Interfaces
- **Defining Object Shapes**: Use interfaces to define the expected structure of an object, such as function parameters or API responses.
- **Code Reusability**: Interfaces can be reused across different parts of your codebase, promoting consistency.
- **Extensibility**: Interfaces can be extended using the `extends` keyword, allowing you to build upon existing structures.
- **Type Checking**: They help catch errors at compile time by enforcing type constraints.
- **Describing Function Types**: Interfaces can also describe the shape of functions, including their parameters and return types.

Example:
```typescript
interface User {
    id: number;
    name: string;
    email: string;
}

function getUserInfo(user: User): string {
    return `User ${user.name} has email ${user.email}`;
}
```

## Classes
```typescript
class Animal {
    name: string;
    constructor(name: string) {
        this.name = name;
    }
    move(distanceInMeters: number = 0) {
        console.log(`${this.name} moved ${distanceInMeters}m.`);
    }
}
```

## Functions

### Regular Function
```typescript
function add(x: number, y: number): number {
    return x + y;
}

let myAdd = function(x: number, y: number): number { return x + y; };
```

### Arrow Functions
Arrow functions provide a concise syntax for writing functions in TypeScript. They are especially useful for maintaining the `this` context in callbacks.

#### Syntax
```typescript
const add = (x: number, y: number): number => {
    return x + y;
};
```

#### Implicit Return
If the function body contains only a single expression, you can omit the braces and the `return` keyword:
```typescript
const multiply = (x: number, y: number): number => x * y;
```

#### Arrow Functions and `this`
Arrow functions do not have their own `this` context. Instead, they inherit `this` from the surrounding scope:
```typescript
class Counter {
    count: number = 0;

    increment = () => {
        this.count++;
    };
}

const counter = new Counter();
counter.increment();
console.log(counter.count); // Output: 1
```

#### Usage in Callbacks
Arrow functions are commonly used in callbacks to avoid issues with `this` binding:
```typescript
const numbers = [1, 2, 3];
const squared = numbers.map(n => n * n);
console.log(squared); // Output: [1, 4, 9]
```

## Generics
```typescript
function identity<T>(arg: T): T {
    return arg;
}

let output = identity<string>("myString");
```

## Enums
```typescript
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

## Type Assertions
```typescript
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
```

## Modules
```typescript
export class MyClass {
    // ...
}

import { MyClass } from "./MyClass";
```

## Utility Types
```typescript
interface Person {
    name: string;
    age: number;
}

type PartialPerson = Partial<Person>;
type ReadonlyPerson = Readonly<Person>;
```