---
tags:
  - Framework
  - ReactNative
---
# React Native Styles

## Table of Contents
- [Basic Syntax](#basic%20syntax)
- [Common Properties](#common%20properties)
    - [Layout](#layout)
    - [Dimensions](#dimensions)
    - [Spacing](#spacing)
    - [Positioning](#positioning)
- [Text Styling](#text%20styling)
- [Background and Borders](#background%20and%20borders)
-[Shadows (iOS/Android)](#Shadows%20(iOS/Android)) 
- [Example Usage](#example%20usage)
- [Tips](#tips)

Further Details:  
- [Flex](Flex.md)

## Basic Syntax
```javascript
import { StyleSheet } from 'react-native';

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
```

## Common Properties

### Layout
- `flex`: Defines the flex-grow factor.
- `flexDirection`: `row` | `column` (default: `column`).
- `justifyContent`: `flex-start` | `center` | `flex-end` | `space-between` | `space-around`.
- `alignItems`: `flex-start` | `center` | `flex-end` | `stretch`.

### Dimensions
- `width`: Number or percentage (`'100%'`).
- `height`: Number or percentage.
- `maxWidth`, `maxHeight`, `minWidth`, `minHeight`.

### Spacing
- `margin`, `marginTop`, `marginBottom`, `marginLeft`, `marginRight`, `marginHorizontal`, `marginVertical`.
- `padding`, `paddingTop`, `paddingBottom`, `paddingLeft`, `paddingRight`, `paddingHorizontal`, `paddingVertical`.

### Positioning
- `position`: `relative` | `absolute`.
- `top`, `bottom`, `left`, `right`.

## Text Styling
- `fontSize`: Number (e.g., `16`).
- `fontWeight`: `normal` | `bold` | `100` to `900`.
- `color`: Hex, RGB, or named color.
- `textAlign`: `left` | `center` | `right`.
- `lineHeight`: Number.
- `textDecorationLine`: `none` | `underline` | `line-through`.

## Background and Borders
- `backgroundColor`: Hex, RGB, or named color.
- `borderWidth`: Number.
- `borderColor`: Hex, RGB, or named color.
- `borderRadius`: Number.
- `borderTopWidth`, `borderBottomWidth`, `borderLeftWidth`, `borderRightWidth`.

## Shadows (iOS/Android)
- `shadowColor`: Color of the shadow (iOS).
- `shadowOffset`: `{ width: number, height: number }` (iOS).
- `shadowOpacity`: Number (iOS).
- `shadowRadius`: Number (iOS).
- `elevation`: Number (Android).

## Example Usage
```javascript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const App = () => (
    <View style={styles.container}>
        <Text style={styles.text}>Hello, React Native!</Text>
    </View>
);

const styles = StyleSheet.create({
    container: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: '#f0f0f0',
    },
    text: {
        fontSize: 20,
        color: '#333',
        fontWeight: 'bold',
    },
});

export default App;
```

## Tips
- Use `StyleSheet.create` for better performance.
- Avoid inline styles for reusability and readability.
- Use percentages for responsive designs.
