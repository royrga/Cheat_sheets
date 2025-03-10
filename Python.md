# Python Cheat Sheet

[Back](README.md) to README file

## Table of Contents
- [Variables and Data Types](#variables-and-data-types)
    - [Data Types Description](#data-types-description)
- [Control Flow](#control-flow)
- [Functions](#functions)
- [Modules and Packages](#modules-and-packages)
- [File Handling](#file-handling)
- [Error Handling](#error-handling)
- [Classes and Objects](#classes-and-objects)
- [Common Built-in Functions](#common-built-in-functions)
- [Advanced tools](#advanced-tools)
    - [List Slicing](#list-slicing)

## Variables and Data Types

- **Variables**: `x = 5`
- **Data Types**: `int`, `float`, `str`, `list`, `tuple`, `dict`, `set`, `bool`

### Data Types Description

- **int**: Integer numbers, e.g., `1`, `2`, `3`
- **float**: Floating-point numbers, e.g., `1.0`, `2.5`, `3.14`
- **str**: String of characters, e.g., `"hello"`, `"world"`
- **list**: Ordered, mutable collection, e.g., `[1, 2, 3]`
- **tuple**: Ordered, immutable collection, e.g., `(1, 2, 3)`
- **dict**: Key-value pairs, e.g., `{"key": "value"}`
- **set**: Unordered collection of unique elements, e.g., `{1, 2, 3}`
- **bool**: Boolean values, `True` or `False`

## Control Flow
- **If Statement**:
    ```python
    if condition:
            # code
    elif another_condition:
            # code
    else:
            # code
    ```
- **For Loop**:
    ```python
    for item in iterable:
            # code
    ```
- **While Loop**:
    ```python
    while condition:
            # code
    ```

## Functions
- **Defining a Function**:
    ```python
    def function_name(parameters):
            # code
            return value
    ```

## Modules and Packages
- **Importing a Module**:
    ```python
    import module_name
    ```
- **Importing Specific Functions**:
    ```python
    from module_name import function_name
    ```

## File Handling
- **Opening a File**:
    ```python
    with open('filename', 'mode') as file:
            # code
    ```

## Error Handling
- **Try-Except Block**:
    ```python
    try:
            # code
    except Exception as e:
            # code
    ```

## Classes and Objects
- **Defining a Class**:
    ```python
    class ClassName:
            def __init__(self, parameters):
                    # code
            def method_name(self):
                    # code
    ```

## Common Built-in Functions
- `print()`
- `len()`
- `range()`
- `type()`
- `str()`
- `int()`
- `float()`
- `list()`
- `dict()`
- `set()`
- `bool()`


## Advanced tools

### List tricks

```python
# List traversal
range(start, stop, hop)
range(n) # [0,1,...,n-1]
range(1,n) # [1,...,n-1]
range(1,n,2) # [1,3,5,...,n-1] if n is even, or [1,3,5,...,n-2] if n is odd
range(n,-1,-1) # [n,n-1,n-2,...,0]
range(len(arr)) # Provides indices of an array arr
range(len(arr)-1,-1,-1) # Provides indices of arr backwards

# List slicing
array[start:stop]
array[start:stop:step]

arr = [1,2,3,4]
arr[1:] = [2,3,4] # Single indexing
arr[:2] = [1,2] # Single indexing
arr[-4:-2] = [1,2] # Negative indexing

arr[0::2] =[1,3] # Step
arr[::-1] =[4,3,2,1] # Reversing array

#List manipulation
arr = [1,2,3]
[str(x) for x in arr] # Output: ['1','2','3']
map(lambda x: str(x), arr) # Output: ['1','2','3']
[str(x) for x in arr if x%2] # Output: ['1','3']

# List as queue
arr = [1,2,3]
arr.append(x) # queue.push(x)
arr.pop(0) #queue.pop()
arr[0] #queue.peek()

# List as stack
arr = [1,2,3]
arr.append(x) #stack.push(x)
arr.pop() # stack.pop()
arr[-1] # stack.peek()
```