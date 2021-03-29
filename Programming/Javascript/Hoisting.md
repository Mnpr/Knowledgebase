Hoisting 

# Hoisting

In this tutorial you will learn about the hoisting behavior of JavaScript.

## What is Hoisting

In JavaScript, all [variable](https://www.tutorialrepublic.com/javascript-tutorial/javascript-variables.php) and [function](https://www.tutorialrepublic.com/javascript-tutorial/javascript-functions.php) declarations are moved or _hoisted_ to the top of their current scope, regardless of where it is defined. This is the default behavior of JavaScript interpreter which is called _hoisting_. In the following sections we'll take a closer look at how it actually works.

## Function Hoisting

Functions that are defined using a function declaration are automatically hoisted. That means they can be called before they have been defined. Let's understand this with an example:

#### Example

```javascript
// Calling function before declaration
sayHello(); // Outputs: Hello, I'm hoisted!

function sayHello() {
    alert("Hello, I'm hoisted!");
}
```

As you can see, we've called the `sayHello()` function before it is defined, but the code still works. This is because the function declaration is hoisted to the top automatically behind the scenes.

* * *

## Variable Hoisting

Similarly, the variable declarations are also hoisted to the top of their current scope automatically. This means that if the variable is declared inside a function block, it will be moved at the top of the function, but if it is declared outside any function it will be moved to top of the script and become globally available. Take a look at the following example, to see how this works:

#### Example

```javascript
str = "Hello World!";
alert(str); // Outputs: Hello World!
var str;
```

However, JavaScript only hoists declarations, not initializations. That means if a variable is declared and initialized after using it, the value will be `undefined`. For example:

#### Example

```javascript
alert(str); // Outputs: undefined
var str;
str = "Hello World!";
```

Here's another example demonstrating the variable hoisting behavior of JavaScript:

#### Example

```javascript
var i = 1; // Declare and initialize i
alert(i + ", " + j); // Outputs: 1, undefined
var j = 2; // Declare and initialize j

var x = 5; // Declare and initialize x
var y; // Declare y
alert(x + ", " + y); // Outputs: 5, undefined
y = 10; // Initialize y

var a = 3; // Declare and initialize a
b = 6; // Initialize b
alert(a + ", " + b); // Outputs: 3, 6
var b; // Declare b

var u = 4; // Declare and initialize u
alert(u + ", " + v); // Outputs: 4, undefined
var v; // Declare v
v = 8; // Initialize v
```

Variable hoisting may seem a little bit confusing at first glance, but if you go through these examples carefully you will easily understand how it works.

**Note:** It is considered best practice to declare your variables at the top of the current scope, because of hoisting behavior. Also, using a variable without declaring is not allowed in [JavaScript strict mode](https://www.tutorialrepublic.com/javascript-tutorial/javascript-strict-mode.php). See the next chapter to learn more about the strict mode.

* * *
