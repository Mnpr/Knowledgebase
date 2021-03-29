Operators

# JavaScript Operators

In this tutorial you will learn how to manipulate or perform the operations on variables and values using the operators in JavaScript.

## What are Operators in JavaScript

Operators are symbols or keywords that tell the JavaScript engine to perform some sort of actions. For example, the addition (`+`) symbol is an operator that tells JavaScript engine to add two variables or values, while the equal-to (`==`), greater-than (`>`) or less-than (`<`) symbols are the operators that tells JavaScript engine to compare two variables or values, and so on.

The following sections describe the different operators used in JavaScript.

## JavaScript Arithmetic Operators

The arithmetic operators are used to perform common arithmetical operations, such as addition, subtraction, multiplication etc. Here's a complete list of JavaScript's arithmetic operators:

| Operator | Description    | Example   | Result                        |
| -------- | -------------- | --------- | ----------------------------- |
| `+`      | Addition       | `$x + $y` | Sum of $x and $y              |
| `-`      | Subtraction    | `$x - $y` | Difference of $x and $y.      |
| `*`      | Multiplication | `$x * $y` | Product of $x and $y.         |
| `/`      | Division       | `$x / $y` | Quotient of $x and $y         |
| `%`      | Modulus        | `$x % $y` | Remainder of $x divided by $y |

The following example will show you these arithmetic operators in action:

#### Example

```javascript
var x = 10;
var y = 4;
alert(x + y); // 0utputs: 14
alert(x - y); // 0utputs: 6
alert(x * y); // 0utputs: 40
alert(x / y); // 0utputs: 2.5
alert(x % y); // 0utputs: 2
```

* * *

## JavaScript Assignment Operators

The assignment operators are used to assign values to variables.

| Operator | Description                | Example  | Is The Same As |
| -------- | -------------------------- | -------- | -------------- |
| `=`      | Assign                     | `x = y`  | `x = y`        |
| `+=`     | Add and assign             | `x += $` | `x = x + y`    |
| `-=`     | Subtract and assign        | `x -= y` | `x = x - y`    |
| `*=`     | Multiply and assign        | `x *= y` | `x = x * y`    |
| `/=`     | Divide and assign quotient | `x /= y` | `x = x / y`    |
| `%=`     | Divide and assign modulus  | `x %= y` | `x = x % y`    |

The following example will show you these assignment operators in action:

#### Example

```javascript
var x;    // Declaring Variable

x = 10;
alert(x); // Outputs: 10

x = 20;
x += 30;
alert(x); // Outputs: 50

x = 50;
x -= 20;
alert(x); // Outputs: 30

x = 5;
x *= 25;
alert(x); // Outputs: 125

x = 50;
x /= 10;
alert(x); // Outputs: 5

x = 100;
x %= 15;
alert(x); // Outputs: 10
```

* * *

## JavaScript String Operators

There are two operators which can also used be for strings.

| Operator | Description              | Example        | Result                         |
| -------- | ------------------------ | -------------- | ------------------------------ |
| `+`      | Concatenation            | `str1 + str2`  | Concatenation of str1 and str2 |
| `+=`     | Concatenation assignment | `str1 += str2` | Appends the str2 to the str1   |

The following example will show you these string operators in action:

#### Example

```javascript
var str1 = "Hello";
var str2 = " World!";

alert(str1 + str2); // Outputs: Hello World!

str1 += str2;
alert(str1); // Outputs: Hello World!
```

* * *

## JavaScript Incrementing and Decrementing Operators

The increment/decrement operators are used to increment/decrement a variable's value.

| Operator | Name           | Effect                              |
| -------- | -------------- | ----------------------------------- |
| `++x`    | Pre-increment  | Increments x by one, then returns x |
| `x++`    | Post-increment | Returns x, then increments x by one |
| `--x`    | Pre-decrement  | Decrements x by one, then returns x |
| `x--`    | Post-decrement | Returns x, then decrements x by one |

The following example will show you how increment and decrement operators actually work:

#### Example

```javascript
var x; // Declaring Variable

x = 10;
alert(++x); // Outputs: 11
alert(x);   // Outputs: 11

x = 10;
alert(x++); // Outputs: 10
alert(x);   // Outputs: 11

x = 10;
alert(--x); // Outputs: 9
alert(x);   // Outputs: 9

x = 10;
alert(x--); // Outputs: 10
alert(x);   // Outputs: 9
```

* * *

## JavaScript Logical Operators

The logical operators are typically used to combine conditional statements.

| Operator | Name | Example  | Result                        |
| -------- | ---- | -------- | ----------------------------- |
| `&&`     | And  | `x && y` | True if both x and y are true |
| `\|`     | Or   | `x \| y` | True if either x or y is true |
| `!`      | Not  | `!x`     | True if x is not true         |

The following example will show you how these logical operators actually work:

#### Example

```javascript
var year = 2018;

// Leap years are divisible by 400 or by 4 but not 100
if((year % 400 == 0) || ((year % 100 != 0) && (year % 4 == 0))){
    alert(year + " is a leap year.");
} else{
    alert(year + " is not a leap year.");
}
```

* * *

## JavaScript Comparison Operators

The comparison operators are used to compare two values in a Boolean fashion.

| Operator | Name                     | Example   | Result                                                                                                                                   |
| -------- | ------------------------ | --------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| `==`     | Equal                    | `x == y`  | True if x is equal to y                                                                                                                  |
| `===`    | Identical                | `x === y` | True if x is equal to y, and they are of the same [type](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php) |
| `!=`     | Not equal                | `x != y`  | True if x is not equal to y                                                                                                              |
| `!==`    | Not identical            | `x !== y` | True if x is not equal to y, or they are not of the same type                                                                            |
| `<`      | Less than                | `x < y`   | True if x is less than y                                                                                                                 |
| `>`      | Greater than             | `x > y`   | True if x is greater than y                                                                                                              |
| `>=`     | Greater than or equal to | `x >= y`  | True if x is greater than or equal to y                                                                                                  |
| `<=`     | Less than or equal to    | `x <= y`  | True if x is less than or equal to y                                                                                                     |

The following example will show you these comparison operators in action:

#### Example

```javascript
var x = 25;
var y = 35;
var z = "25";

alert(x == z);  // Outputs: true
alert(x === z); // Outputs: false
alert(x != y);  // Outputs: true
alert(x !== z); // Outputs: true
alert(x < y);   // Outputs: true
alert(x > y);   // Outputs: false
alert(x <= y);  // Outputs: true
alert(x >= y);  // Outputs: false
```

* * *