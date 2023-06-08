# Atlas Programming Language Documentation

## Table of Contents
1. [Introduction](#introduction)
2. [Syntax](#syntax)
3. [Functions](#functions)
   1. [oopify](#oopify)
   2. [join](#join)
   3. [map](#map)
4. [Statements](#statements)
   1. [PRINT](#print)
   2. [FOR](#for)
5. [Examples](#examples)

## Introduction <a name="introduction"></a>
Atlas is a programming language designed to provide a simple and concise syntax for performing various operations. It aims to make programming tasks efficient and enjoyable. This documentation provides a comprehensive guide to the Atlas programming language, including its syntax, built-in functions, and example code snippets.

## Syntax <a name="syntax"></a>
Atlas uses a C-like syntax with indentation-based block structure. Statements and expressions are terminated with a newline character. The following are the basic elements of the Atlas syntax:

- Variables: Declared using the `VAR` keyword followed by the variable name.
- Assignment: Assign values to variables using the `=` operator.
- Functions: Defined using the `FUN` keyword, followed by the function name and parameter list.
- Control Flow: Atlas supports `IF-THEN` conditional statements and `FOR` loops.

## Functions <a name="functions"></a>
Atlas allows you to define custom functions to encapsulate reusable code. Functions are declared using the `FUN` keyword, followed by the function name and parameter list in parentheses. The function body is defined within a block, denoted by indentation. Here are the details of the functions used in the provided code:

### oopify(prefix) <a name="oopify"></a>
The `oopify` function takes a `prefix` string as a parameter and returns the concatenation of the `prefix` with the string "oop". It can be defined as follows:

```atlas
FUN oopify(prefix)
    RETURN prefix + "oop"
END
```

### join(elements, separator) <a name="join"></a>
The `join` function takes a list of `elements` and a `separator` string as parameters. It concatenates all the elements with the separator and returns the resulting string. The function can be defined as follows:

```atlas
FUN join(elements, separator)
    VAR result = ""
    VAR len = LEN(elements)

    FOR i = 0 TO len THEN
        VAR result = result + elements/i
        IF i != len - 1 THEN VAR result = result + separator
    END

    RETURN result
END
```

### map(elements, func) <a name="map"></a>
The `map` function takes a list of `elements` and a `func` function as parameters. It applies the `func` to each element of the list and returns a new list containing the results. The function can be defined as follows:

```atlas
FUN map(elements, func)
    VAR new_elements = []

    FOR i = 0 TO LEN(elements) THEN
        APPEND(new_elements, func(elements/i))
    END

    RETURN new_elements
END
```

## Statements <a name="statements"></a>
Atlas provides various statements to perform specific actions within the code.

### PRINT <a name="print"></a>
The `PRINT` statement is used to output a value to the console. It can accept a single argument or multiple arguments separated by commas. Here is an example:

```atlas
PRINT("Greetings universe!")
```

### FOR <a name="for"></a>
The `FOR` statement is used to create loops in Atlas. It allows you

 to repeat a block of code a specified number of times. The general syntax is as follows:

```atlas
FOR variable = start_value TO end_value THEN
    // Code block
END
```

In the provided code snippet, the `FOR` loop is used to iterate from 0 to 5.

## Examples <a name="examples"></a>
Here are a few examples demonstrating the usage of the functions and statements described above:

```atlas
PRINT(join(map(["l", "sp"], oopify), ", "))

FOR i = 0 TO 5 THEN
    PRINT(join(map(["l", "sp"], oopify), ", "))
END
```

The above code will produce the following output:

```
loop, scoop
loop, scoop
loop, scoop
loop, scoop
loop, scoop
loop, scoop
```

This concludes the detailed documentation for the Atlas programming language. The provided functions and statements should give you a good starting point for using Atlas effectively. Happy coding with Atlas!
