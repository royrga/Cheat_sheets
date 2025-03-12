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
    - [List Comprehension](#list-comprehension)

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

    ### More on Classes

    - **`__init__` Method**:
        The `__init__` method is the constructor method in Python. It is called when an instance (object) of the class is created. The `self` parameter refers to the instance being created.
        ```python
        class Person:
            def __init__(self, name, age):
                self.name = name
                self.age = age

        person1 = Person("Alice", 30)
        print(person1.name)  # Output: Alice
        print(person1.age)   # Output: 30
        ```

    - **Basic Magic Methods**:
        Magic methods (also known as dunder methods) are special methods that start and end with double underscores. They allow you to define the behavior of your objects for built-in operations.

        - **`__str__` and `__repr__`**:
            ```python
            class Person:
                def __init__(self, name, age):
                    self.name = name
                    self.age = age

                def __str__(self):
                    return f"Person(name={self.name}, age={self.age})"

                def __repr__(self):
                    return f"Person('{self.name}', {self.age})"

            person1 = Person("Alice", 30)
            print(person1)  # Output: Person(name=Alice, age=30)
            ```

        - **`__eq__` and `__lt__`**:
            ```python
            class Person:
                def __init__(self, name, age):
                    self.name = name
                    self.age = age

                def __eq__(self, other):
                    return self.age == other.age

                def __lt__(self, other):
                    return self.age < other.age

            person1 = Person("Alice", 30)
            person2 = Person("Bob", 25)
            print(person1 == person2)  # Output: False
            print(person1 < person2)   # Output: False
            ```

        - **`__len__` and `__getitem__`**:
            ```python
            class MyList:
                def __init__(self, items):
                    self.items = items

                def __len__(self):
                    return len(self.items)

                def __getitem__(self, index):
                    return self.items[index]

            my_list = MyList([1, 2, 3, 4])
            print(len(my_list))       # Output: 4
            print(my_list[2])         # Output: 3
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

### List Comprehension

- **Basic Syntax**:
    ```python
    [expression for item in iterable]
    ```
- **With Condition**:
    ```python
    [expression for item in iterable if condition]
    ```
- **Nested List Comprehension**:
    ```python
    [[expression for item in iterable] for iterable in outer_iterable]
    ```

**Examples**:
- **Square Numbers**:
    ```python
    squares = [x**2 for x in range(10)]
    ```
- **Filter Even Numbers**:
    ```python
    evens = [x for x in range(10) if x % 2 == 0]
    ```
- **Flatten a List of Lists**:
    ```python
    nested_list = [[1, 2, 3], [4, 5, 6]]
    flat_list = [item for sublist in nested_list for item in sublist]
    ```

    ## Unpacking Operator

    The unpacking operator (`*` and `**`) in Python allows you to unpack iterables and dictionaries.

    ### Unpacking Iterables

    - **Using `*` to unpack a list or tuple**:
        ```python
        numbers = [1, 2, 3]
        print(*numbers)  # Output: 1 2 3
        ```

    - **Using `*` in function arguments**:
        ```python
        def add(a, b, c):
            return a + b + c

        numbers = [1, 2, 3]
        print(add(*numbers))  # Output: 6
        ```

    - **Unpacking with multiple variables**:
        ```python
        a, *b, c = [1, 2, 3, 4, 5]
        print(a)  # Output: 1
        print(b)  # Output: [2, 3, 4]
        print(c)  # Output: 5
        ```

    ### Unpacking Dictionaries

    - **Using `**` to unpack a dictionary**:
        ```python
        def print_info(name, age):
            print(f"Name: {name}, Age: {age}")

        info = {"name": "Alice", "age": 30}
        print_info(**info)  # Output: Name: Alice, Age: 30
        ```

    - **Merging dictionaries**:
        ```python
        dict1 = {'a': 1, 'b': 2}
        dict2 = {'c': 3, 'd': 4}
        merged_dict = {**dict1, **dict2}
        print(merged_dict)  # Output: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
        ```

    ### Using Unpacking in Function Calls

    - **Combining positional and keyword arguments**:
        ```python
        def func(a, b, c, d):
            print(a, b, c, d)

        args = (1, 2)
        kwargs = {'c': 3, 'd': 4}
        func(*args, **kwargs)  # Output: 1 2 3 4
        ```