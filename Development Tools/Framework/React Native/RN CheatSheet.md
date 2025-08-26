---
tags:
  - ReactNative
  - Framework
---

# React Native Cheat Sheet

## Table of contents

- [Component Template (TypeScript)](#component-template-typescript)
- [map() ](#map-method-typescript)
    - [Syntax](#syntax)
    - [Example](#example)
    - [Example with Objects](#example-with-objects)
    - [Notes](#notes)



## Component Template (TypeScript)

Below is a template for creating a React Native component using TypeScript.

```typescript
import { FC } from 'react';
import { View, Text, StyleSheet } from 'react-native';

interface Props {
    // Define your props here
    title: string;
}

const MyComponent: React.FC<Props> = ({ title }) => {
    return (
        <View style={styles.container}>
            <Text style={styles.text}>{title}</Text>
        </View>
    );
};

const styles = StyleSheet.create({
    container: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: '#fff',
    },
    text: {
        fontSize: 16,
        color: '#333',
    },
});

export default MyComponent;
```s


#  map() Method (TypeScript)

The `map()` method creates a new array populated with the results of calling a provided function on every element in the calling array.

## Syntax

```typescript
array.map(callbackFn, thisArg?)
```

- `callbackFn`: A function that is called for every element in the array. It takes three arguments:
    - `currentValue`: The current element being processed.
    - `index` (optional): The index of the current element.
    - `array` (optional): The array `map` was called upon.
- `thisArg` (optional): Value to use as `this` when executing `callbackFn`.

## Example

```typescript
const numbers: number[] = [1, 2, 3, 4];
const doubled: number[] = numbers.map((num) => num * 2);

console.log(doubled); // Output: [2, 4, 6, 8]
```

## Example with Objects

```typescript
interface User {
        id: number;
        name: string;
}

const users: User[] = [
        { id: 1, name: 'Alice' },
        { id: 2, name: 'Bob' },
];

const userNames: string[] = users.map((user) => user.name);

console.log(userNames); // Output: ['Alice', 'Bob']
```

## Notes

- The `map()` method does not mutate the original array.
- It is commonly used for transforming data in arrays.

