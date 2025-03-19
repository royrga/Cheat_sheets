# TypeScript Cheat Sheet
[Back](README.md) to README file
## Table of Contents
1. [Basic Types](#basic-types)
2. [Interfaces](#interfaces)
3. [Classes](#classes)
4. [Functions](#functions)
5. [Generics](#generics)
6. [Enums](#enums)
7. [Type Assertions](#type-assertions)
8. [Modules](#modules)
9. [Utility Types](#utility-types)

## Basic Types
```typescript
let isDone: boolean = false;
let decimal: number = 6;
let color: string = "blue";
let list: number[] = [1, 2, 3];
let x: [string, number] = ["hello", 10];
```

## Interfaces
```typescript
interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
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
```typescript
function add(x: number, y: number): number {
    return x + y;
}

let myAdd = function(x: number, y: number): number { return x + y; };
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

## Concepts definition

### Hooks
Hooks in TypeScript are not a built-in feature of the language itself but are commonly associated with React when using TypeScript. They are special functions that let you "hook into" React state and lifecycle features in functional components. Examples include `useState`, `useEffect`, and `useContext`. TypeScript enhances hooks by providing type safety, allowing you to define the types of state, props, and return values for better code reliability and maintainability.