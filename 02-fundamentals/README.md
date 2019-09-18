# JavaScript Language Fundamentals <!-- omit in toc -->

- [Intro & File Setup](#intro--file-setup)
- [Using the Console](#using-the-console)
- [Variables](#variables)
- [Data Types in JavaScript](#data-types-in-javascript)
- [Type Conversion](#type-conversion)
- [Numbers & Math Object](#numbers--math-object)
- [String Methods & Concatenation](#string-methods--concatenation)
- [Template Literals](#template-literals)

## Intro & File Setup

Two methods to connect JavaScript code to HTML document:

1. Internally within HTML file
2. Externally by creating a `.js` file and adding a script source within HTML file

```html
<!-- Method 1 -->
<script>
  alert('Hello');
</Script>

<!-- Method 2 -->
<script src="app.js"></script>
<script src="js/app.js"></script> <!-- if js file is inside js folder-->
```

**Note**: Avoid Method 1 unless it is one or two lines of JavaScript code being used.


## Using the Console

### Accessing the JavaScript Console

- console provides us a way to output our code on the console to test and debug our code
- `alert()` function in JavaScript triggered an alert messagebox in the browser; however, this is not a great way to do things and we can now use the JavaScript console to debug/test our code
- press `F12 key` to open the JavaScript console, by default it will be on the Element tab, then select Console

### JavaScript Console Basics

You can write and execute JavaScript code within the browser console itself

- `alert('Hello World');` displays an alert box with the text Hello in the browser
- `undefined` means nothing was returned from executed code
- if you type a number, console will return it, ff you type `4 + 4` it will return 8
- you can select from the DOM by targetting `document` and it will return the HTML document structure
- what you can do within JavaScript file, can do it within the JavaScript console also
- when you reload the browser, you code will be gone, it's usually used for debugging/testing JavaScript code before committing it in a JavaScript file

### JavaScript Comments

- computer will skip comments
- comments are for humans to read
- notes for the future maintainer

```js
// Single line comments.

/* Multi-
line
comments */
```

### Console and other functions

- `console.log()` is very useful when testing and debugging codes
- `console.table();` create a table for objects
- `console.error();` create an error log
- `consoe.warn();` create a warn log
- `console.clear();` clear the console
- `console.time();` and `console.timeEnd()` must use together and have the same identifier to calculate the time it takes to execute the block of code witin the two functions

### Browser Indication

1. Number and Boolean values are in blue text, other (E.g. Strings) are in black text
2. Arrays, Objects, Tables, Error, Warnings have an arrow which allows you to view more information within the console


## Variables

### Variable Keywords

Three keywords for declaring a variable in JavaScript

- `var` keyword has been around since the beginning of JavaScript
- `let` & `const` which were introduced in ES2015 (ES6) which was an update to the JavaScript language that included many new features
  - are now fully supported in brosers and so stay away from `var` for modern JavaScript
  - also have a big advantage when it comes to block level scope

### Variable Declaration

- use one of the variable keywords and a variable name to declare a variable, then equal (`=`) sign and the data you want to assign to the variable
- initialize a variable without assigning any value, then assign a value later which only applies to `var` and `let`
- reason for just initializing variables is, if we need it for conditionals, E.g. `if` statement which will set the variable depending on the condition

### Variable Rules and Conventions

- variable names can include letters, numbers, underscore(`_`) and dollar (`$`) sign
- variables cannot start with a _number_
- **camelCase** is the recommended the JavaScript naming convention
- **under_score**
- **PascalCase** is recommended for OOP, E.g. constructor function or ES6 classes
- **lowercase**

### let Keyword

`let` works very similar to the `var` and is identical in the global scope; however, it has advantages over `var` when it comes to the block scope.

### `const` Keyword

- `const` or constant is a variable that cannot be changed or reassigned a new value
- when `const` is used for Arrays, Objects and other types of data that are primitive like strings and numbers (i.e things that can change but cannot be reassigned), we are able to change the values
- cannot reassign the value but we can change/mutate array/object properties
- can add/change the array/objects but cannot reassign/re-declare the array or object 

### Conclusion & Recommendation

It is you as the developer to make a decision as to when to use let and `const` and how to declare your variable within your code. It is all by preference.

use `const` unless:

1. the value is changing, 
2. you need to init a variable or 
3. you are using the variable in a iterator for a loop

Using `const` lets your program or anyone else who is looking at your code, know that the variable should not be reassigned. It can be mutated if its an array or object, but it cannot be reassigned as a new primitive value. This will make your code more robust, secure and more readable.


## Data Types in JavaScript

There are a bunch of different data types but there are _Two Types_ of data types:

- Primitive Data Types
- Reference Data Types


### Primitive Data Types

- Stored directly in the location the variable accesses
- Stored on the stack , when you access a primitive data type you access it by its actual value

**6 Primitive Data Types**:

1. **String** a sequence of characters
2. **Number** a number (integers, decimals, floats are all consindered as numbers)
3. **Boolean** true or false (1 or 0)
4. **Null** intentional empty value
5. **Undefined** a variable that has not been assigned a value
6. **Symbols** (ES6)

### Reference Data Types

- Objects accessed by reference
- Objects that are stored on the heap
- A pointer to a location in memory

The data isn't actually stored in the variable its stored on what is called the heap (to do with dynamically allocated memory - advanced topic to research later on).

Reference Data Types are not accessed by the actual (primitve) value, they are accessed by reference. They are also considered as objects.

**5 Reference Data Types / Objects**:

- **Arrays**
- **Object Leterals**
- **Functions**
- **Dates**
- Anything else

### Dynamically Typed Language

- Types are associated with values not variables
- The same variable can hold multiple types (E.g. variable can hold a string then set to a number without any errors or issues)
- We do not need to specify types
- Most other languages are statically typed (E.g. Java, C#, C++)
- There are superets of JavaScript and addons to allow static typing (E.g. TypScript, Flow)


## Type Conversion

Type conversion is the process of taking a variable and changing its data type.

### Convert to a String

Two ways to convert data types into strings:

1. `String()` function
2. `toString()` method

We can convert the following data types to a string:

- numbers (and expressions)
- booleans
- dates
- arrays

`.length` property only works on Strings and returns the number of characters of the string.

### Convert to a Number

Two ways to convert data types into number:

1. `Number()` function
2. `parseInt()` & `parseFloat()` methods

We can convert the following data types to a number:

- strings
- boolean (1 = true, 0 = false)
- Null (0)

`.tofixed()` property only works on Number and returns the number as a decimal/float number based on the number within the parentheses (if left blank then no decimal point).

`NaN` will returm when we try to convert a string or an array to a number, stands for **Not a Number**

`parseInt()` will return a integer number whereas `parseFloat()` will return a decimal number.

### Type Coercion

**Type coercion** is the process of converting value from one type to another however, JavaScript will do this for us.

This is where we try to convert a data type to another data type; however, we allow JavaScript to do this for us. For example: we try to add a string to a number


## Numbers & Math Object

### Basic Math with Numbers

Basic math operators:

- (`+`) Addition
- (`+`) Subtraction
- (`+`) Multiplication
- (`+`) Division
- (`+`) Modulus

### Math Object

**Math Object** allows us to do math functions such as round a number, find the absolute, powers, generate random numbers etc.

`Math` is an Object that has properties and methods. The Math Object have methods and functions built into the JavaScript language which we can utilise when we call the Math Object.

- **property** is an attribute
- **method** is a function inside of an object

### Some Math Object properties and methods

- `Math.PI` represents the ratio of the circumference of a circle to its diameter, E.g. `3.141592653589793`
- `Math.E` or Euler's Numbers represents the base of natural logarithms, E.g.`2.718281828459045`
- `Math.round()`  returns the value of a number rounded to the nearest integer
- `Math.ceil()` returns the smallest integer greater than or equal to a given number
- `Math.floor()` returns the largest integer less than or equal to a given number
- `Math.sqrt()` returns the square root of a number
- `Math.abs()` return it's absolute/positive number
- `Math.pow()` returns the `base` to the `exponent` power, that is, `base`<sup>`exponent`</sup>
- `Math.min()` returns the lowest-valued number
- `Math.max()` returns the largest of zero or more numbers
- `Math.random()` returns a floating-point, pseudo-random number in the range `0–1`


## String Methods & Concatenation

### Concatenation

Concatenation allows you to join string variables together, using `+` or `+=` operators.

**Note**: Different data types can be concatenated together, does not necessarily have to be a string data type.

Append means to add onto a variable and not replace it. Use (`+=`) append a variable.

**Note**: Be consistant when using quotes within your code. Use escaping (backslash (`\`)) when using single quotes.

### String Properties & Methods

Similar to Numbers, String has built-in properties and methods, E.g. `length`, `toUpperCase()`;

- `length` indicates the length of a string
- `concat()` concatenates the string arguments to the calling string and returns a new string
- `toUpperCase` returns the calling string value converted to uppercase
- `toLowerCase()` returns the calling string value converted to lower case
- `indexOf()` returns the index within the calling String of the first occurrence of the specified value, else will return -1
- `lastIndexOf()` returns the index within the calling String object of the last occurrence of the specified value, else  will return -1
- `charAt()` returns the character at the specified index in a string
  - get last char by `length - 1`
- `substring()` returns the part of the string between the start and end indexes, or to the end of the string
- `slice()` extracts a section of a string and returns it as a new string, without modifying the original string
  - slice from left to right, E.g. `slice(-3)`
  - slice from right to left (negative number = return last x letters from the string)
- `split()` splits a String into an array of strings by separating the string into substrings, using a specified separator string to determine where to make each split
- `replace()` returns a new string with some or all matches of a pattern replaced by a replacement
- `includes()` determines whether one string may be found within another string, returning `true` or `false`

To distinguish a property from a method:

- properties do not have brackets (`()`) at the end, E.g. `length`
- methods has brackets (`()`)  at the end, E.g. `toUpperCase()`


## Template Literals

**Template literals** are string literals allowing embedded expressions. You can use multi-line strings and string interpolation features with them.

Instead of using single (`'`) or double (`"`) quotes we can use back-ticks (`) to indicate a Template Literal. Anything with the back-ticks can be written as normal HTML tags.

To enter a JavaScript variable, we can use the syntax `${variableName}` instead of a bunch of `+`.

We can also add JavaScript:

- Expressions, E.g. `${2 + 2}`
- Functions, E.g. `${hello()}`
- Conditionals, E.g. `${age > 30 ? 'Over 30' : 'Under 30'}`

Template Literals (template strings) method allows for easy concatenation of HTML strings and the syntax is more cleaner and readable.