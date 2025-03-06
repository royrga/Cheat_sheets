# Python Cheat Sheet
[Back](README.md) to README file
## Table of Contents
1. [Variables and Data Types](#variables-and-data-types)
2. [Control Flow](#control-flow)
3. [Functions](#functions)
4. [Modules and Packages](#modules-and-packages)
5. [File Handling](#file-handling)
6. [Error Handling](#error-handling)
7. [Classes and Objects](#classes-and-objects)
8. [Common Built-in Functions](#common-built-in-functions)

## Variables and Data Types
- **Variables**: `x = 5`
- **Data Types**: `int`, `float`, `str`, `list`, `tuple`, `dict`, `set`, `bool`

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