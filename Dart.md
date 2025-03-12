# Dart Cheat Sheet

## Table of Contents
- [Basics](#basics)
    - [Variables](#variables)
    - [Constants](#constants)
    - [Functions](#functions)
- [Control Flow](#control-flow)
    - [If-Else](#if-else)
    - [Switch](#switch)
    - [Loops](#loops)
- [Collections](#collections)
    - [Lists](#lists)
    - [Sets](#sets)
    - [Maps](#maps)
- [Classes](#classes)
    - [Basic Class](#basic-class)
    - [Inheritance](#inheritance)
- [Asynchronous Programming](#asynchronous-programming)
    - [Future](#future)
    - [Stream](#stream)
- [Exception Handling](#exception-handling)

## Basics

### Variables
```dart
var name = 'John';
int age = 30;
double height = 5.9;
bool isStudent = true;
String city = 'New York';
```

### Constants
```dart
const pi = 3.14;
final currentTime = DateTime.now();
```

### Functions
```dart
void main() {
        print(greet('Alice'));
}

String greet(String name) {
        return 'Hello, $name!';
}
```

## Control Flow

### If-Else
```dart
if (age > 18) {
        print('Adult');
} else {
        print('Minor');
}
```

### Switch
```dart
switch (day) {
        case 'Monday':
                print('Start of the week');
                break;
        case 'Friday':
                print('End of the week');
                break;
        default:
                print('Midweek');
}
```

### Loops
```dart
for (var i = 0; i < 5; i++) {
        print(i);
}

while (isStudent) {
        print('Studying...');
        isStudent = false;
}
```

## Collections

### Lists
```dart
var numbers = [1, 2, 3, 4, 5];
numbers.add(6);
print(numbers[0]);
```

### Sets
```dart
var uniqueNumbers = {1, 2, 3, 4, 5};
uniqueNumbers.add(6);
print(uniqueNumbers.contains(1));
```

### Maps
```dart
var person = {
        'name': 'John',
        'age': 30,
        'city': 'New York'
};
print(person['name']);
```

## Classes

### Basic Class
```dart
class Person {
        String name;
        int age;

        Person(this.name, this.age);

        void greet() {
                print('Hello, my name is $name and I am $age years old.');
        }
}

void main() {
        var person = Person('Alice', 25);
        person.greet();
}
```

### Inheritance
```dart
class Student extends Person {
        String school;

        Student(String name, int age, this.school) : super(name, age);

        @override
        void greet() {
                super.greet();
                print('I study at $school.');
        }
}

void main() {
        var student = Student('Bob', 20, 'XYZ University');
        student.greet();
}
```

## Asynchronous Programming

### Future
```dart
Future<String> fetchData() async {
        return 'Data fetched';
}

void main() async {
        var data = await fetchData();
        print(data);
}
```

### Stream
```dart
Stream<int> countStream(int max) async* {
        for (int i = 1; i <= max; i++) {
                yield i;
        }
}

void main() async {
        await for (var value in countStream(5)) {
                print(value);
        }
}
```

## Exception Handling
```dart
try {
        var result = 10 ~/ 0;
} catch (e) {
        print('Error: $e');
} finally {
        print('This is always executed');
}
```
