# Flex

React Native uses the `flexbox` layout system to create responsive and adaptive UI designs. Below are the key flex parameters and their usage:

![Alt Text](flex_terms.png)

## 1. `flex`
The `flex` property determines how a component grows or shrinks to fill available space.

- **Usage**: 
    ```javascript
    style={{ flex: 1 }}
    ```
- **Description**: 
    - A value of `1` makes the component expand to fill available space.
    - A value of `0` means the component will not grow or shrink.

## 2. `flexDirection`
Defines the primary axis direction along which children are placed.

- **Values**:
    - `row`: Horizontal layout (left to right).
    - `column`: Vertical layout (top to bottom, default).
    - `row-reverse`: Horizontal layout (right to left).
    - `column-reverse`: Vertical layout (bottom to top).

- **Usage**:
    ```javascript
    style={{ flexDirection: 'row' }}
    ```

## 3. `justifyContent`
Aligns children along the primary axis.

- **Values**:
    - `flex-start` (default): Align items to the start.
    - `center`: Center items.
    - `flex-end`: Align items to the end.
    - `space-between`: Distribute items with space between them.
    - `space-around`: Distribute items with space around them.
    - `space-evenly`: Distribute items with equal space around.

- **Usage**:
    ```javascript
    style={{ justifyContent: 'center' }}
    ```

## 4. `alignItems`
Aligns children along the cross-axis.

- **Values**:
    - `flex-start`: Align items to the start of the cross-axis.
    - `center`: Center items on the cross-axis.
    - `flex-end`: Align items to the end of the cross-axis.
    - `stretch` (default): Stretch items to fill the container.

- **Usage**:
    ```javascript
    style={{ alignItems: 'stretch' }}
    ```

## 5. `alignSelf`
Overrides `alignItems` for a specific child.

- **Values**:
    - Same as `alignItems` values.
    - `auto` (default): Inherits from `alignItems`.

- **Usage**:
    ```javascript
    style={{ alignSelf: 'flex-end' }}
    ```

## 6. `flexWrap`
Determines whether children should wrap onto multiple lines.

- **Values**:
    - `nowrap` (default): No wrapping.
    - `wrap`: Wrap items onto multiple lines.
    - `wrap-reverse`: Wrap items in reverse order.

- **Usage**:
    ```javascript
    style={{ flexWrap: 'wrap' }}
    ```

## 7. `gap`, `rowGap`, `columnGap` (React Native 0.71+)
Defines spacing between children.

- **Usage**:
    ```javascript
    style={{ gap: 10, rowGap: 5, columnGap: 5 }}
    ```

## Example
```javascript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const FlexExample = () => {
    return (
        <View style={styles.container}>
            <View style={styles.box1}><Text>Box 1</Text></View>
            <View style={styles.box2}><Text>Box 2</Text></View>
            <View style={styles.box3}><Text>Box 3</Text></View>
        </View>
    );
};

const styles = StyleSheet.create({
    container: {
        flex: 1,
        flexDirection: 'row',
        justifyContent: 'space-around',
        alignItems: 'center',
    },
    box1: { flex: 1, backgroundColor: 'red', padding: 10 },
    box2: { flex: 2, backgroundColor: 'blue', padding: 10 },
    box3: { flex: 1, backgroundColor: 'green', padding: 10 },
});

export default FlexExample;
```

This example demonstrates the use of `flex`, `flexDirection`, `justifyContent`, and `alignItems` to create a responsive layout.