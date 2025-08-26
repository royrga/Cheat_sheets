---
tags:
  - ProgrammingLanguage
---

# Processing Language Cheat Sheet

## Table of Contents

1. [Introduction](#introduction)
2. [Basic Syntax](#basic%20syntax)
3. [Drawing Shapes](#drawing%20shapes)
4. [Color](#color)
5. [Control Structures](#control%20structures)
6. [Functions](#functions)
7. [Arrays](#arrays)
8. [Libraries](#libraries)
9. [Events](#events)
10. [Tips and Tricks](#tips%20and%20tricks)

> To build and run without using the IDE, processing provides a tool for command line interface:
> [Processing CLI](Processing%20CLI.md)  
## Introduction

Processing is a flexible software sketchbook and a language for learning how to code within the context of the visual arts.

## Basic Syntax

- **Setup and Draw Functions**:

    ```java
    void setup() {
        size(400, 400);
    }

    void draw() {
        background(220);
    }
    ```

## Drawing Shapes

- **Ellipse**:

    ```java
    ellipse(x, y, width, height);
    ```

- **Rectangle**:

    ```java
    rect(x, y, width, height);
    ```

## Color

- **Setting Colors**:

    ```java
    fill(r, g, b);
    stroke(r, g, b);
    ```

## Control Structures

- **If Statement**:

    ```java
    if (condition) {
        // code
    }
    ```

- **For Loop**:

    ```java
    for (int i = 0; i < 10; i++) {
        // code
    }
    ```

## Functions

- **Defining Functions**:

    ```java
    void myFunction() {
        // code
    }
    ```

## Arrays

- **Creating Arrays**:

    ```java
    int[] array = new int[10];
    ```

## Libraries

- **Importing Libraries**:

    ```java
    import processing.sound.*;
    ```

## Events

- **Mouse Events**:

    ```java
    void mousePressed() {
        // code
    }
    ```

## Tips and Tricks

- **Commenting Code**:

    ```java
    // This is a single-line comment
    /* This is a multi-line comment */
    ```
