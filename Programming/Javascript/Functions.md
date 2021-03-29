Functions


# JavaScript Functions

## What is Function?

A function is a group of statements that perform specific tasks and can be kept and maintained separately form main program. Functions provide a way to create reusable code packages which are more portable and easier to debug. Here are some advantages of using functions:

*   **Functions reduces the repetition of code within a program** — Function allows you to extract commonly used block of code into a single component. Now you can perform the same task by calling this function wherever you want within your script without having to copy and paste the same block of code again and again.
*   **Functions makes the code much easier to maintain** — Since a function created once can be used many times, so any changes made inside a function automatically implemented at all the places without touching the several files.
*   **Functions makes it easier to eliminate the errors** — When the program is subdivided into functions, if any error occur you know exactly what function causing the error and where to find it. Therefore, fixing errors becomes much easier.

The following section will show you how to define and call functions in your scripts.

## Defining and Calling a Function

The declaration of a function start with the `function` keyword, followed by the name of the function you want to create, followed by parentheses i.e. `()` and finally place your function's code between curly brackets `{}`. Here's the basic syntax for declaring a function:

function functionName() {  
    // Code to be executed  
}

Here is a simple example of a function, that will show a hello message:

#### Example

```javascript
// Defining function
function sayHello() {
    alert("Hello, welcome to this website!");
}
 
// Calling function
sayHello(); // 0utputs: Hello, welcome to this website!
```

Once a function is defined it can be called (invoked) from anywhere in the document, by typing its name followed by a set of parentheses, like `sayHello()` in the example above.

**Note:** A function name must start with a letter or underscore character not with a number, optionally followed by the more letters, numbers, or underscore characters. Function names are case sensitive, just like variable names.

* * *

## Adding Parameters to Functions

You can specify parameters when you define your function to accept input values at run time. The parameters work like placeholder variables within a function; they're replaced at run time by the values (known as argument) provided to the function at the time of invocation.

Parameters are set on the first line of the function inside the set of parentheses, like this:

function functionName(_parameter1_, _parameter2_, _parameter3_) {  
    // Code to be executed  
}

The `displaySum()` function in the following example takes two numbers as arguments, simply add them together and then display the result in the browser.

#### Example

```javascript
// Defining function
function displaySum(num1, num2) {
    var total = num1 + num2;
    alert(total);
}
 
// Calling function
displaySum(6, 20); // 0utputs: 26
displaySum(-5, 17); // 0utputs: 12
```

You can define as many parameters as you like. However for each parameter you specify, a corresponding argument needs to be passed to the function when it is called, otherwise its value becomes `undefined`. Let's consider the following example:

#### Example

```javascript
// Defining function
function showFullname(firstName, lastName) {
    alert(firstName + " " + lastName);
}
 
// Calling function
showFullname("Clark", "Kent"); // 0utputs: Clark Kent
showFullname("John"); // 0utputs: John undefined
```

* * *

## Default Values for Function Parameters ES6

With ES6, now you can specify default values to the function parameters. This means that if no arguments are provided to function when it is called these default parameters values will be used.

#### Example

```javascript
function sayHello(name = 'Guest') {
    alert('Hello, ' + name);
}

sayHello(); // 0utputs: Hello, Guest
sayHello('John'); // 0utputs: Hello, John
```

While prior to ES6, to achieve the same we had to write something like this:

#### Example

```javascript
function sayHello(name) {
    var name = name || 'Guest'; 
    alert('Hello, ' + name);
}

sayHello(); // 0utputs: Hello, Guest
sayHello('John'); // 0utputs: Hello, John
```

To learn about other ES6 features, please check out the [JavaScript ES6 features](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php) chapter.

* * *

## Returning Values from a Function

A function can return a value back to the script that called the function as a result using the `return` statement. The value may be of any type, including arrays and objects.

The `return` statement usually placed as the last line of the function before the closing curly bracket and ends it with a semicolon, as shown in the following example.

#### Example

```javascript
// Defining function
function getSum(num1, num2) {
    var total = num1 + num2;
    return total;
}
 
// Displaying returned value
alert(getSum(6, 20)); // 0utputs: 26
alert(getSum(-5, 17)); // 0utputs: 12
```

A function _can not_ return multiple values. However, you can obtain similar results by returning an [array](https://www.tutorialrepublic.com/javascript-tutorial/javascript-arrays.php) of values, as demonstrated in the following example.

#### Example

```javascript
// Defining function
function divideNumbers(dividend, divisor){
    var quotient = dividend / divisor;
    var arr = [dividend, divisor, quotient];
    return arr;
}
 
// Store returned value in a variable
var all = divideNumbers(10, 2);
 
// Displaying individual values
alert(all[0]); // 0utputs: 10
alert(all[1]); // 0utputs: 2
alert(all[2]); // 0utputs: 5
```

* * *

## Working with Function Expressions

The syntax that we've used before to create functions is called function declaration. There is another syntax for creating a function that is called a function expression.

#### Example

```javascript
// Function Declaration
function getSum(num1, num2) {
    var total = num1 + num2;
    return total;
}
 
// Function Expression
var getSum = function(num1, num2) {
    var total = num1 + num2;
    return total;
};
```

Once function expression has been stored in a variable, the variable can be used as a function:

#### Example

```javascript
var getSum = function(num1, num2) {
    var total = num1 + num2;
    return total;
};
 
alert(getSum(5, 10)); // 0utputs: 15
 
var sum = getSum(7, 25);
alert(sum); // 0utputs: 32
```

**Note:** There is no need to put a semicolon after the closing curly bracket in a function declaration. But function expressions, on the other hand, should always end with a semicolon.

**Tip:** In JavaScript functions can be stored in variables, passed into other functions as arguments, passed out of functions as return values, and constructed at run-time.

The syntax of the _function declaration_ and _function expression_ looks very similar, but they differ in the way they are evaluated, check out the following example:

#### Example

```javascript
declaration(); // Outputs: Hi, I'm a function declaration!
function declaration() {
    alert("Hi, I'm a function declaration!");
}
 
expression(); // Uncaught TypeError: undefined is not a function
var expression = function() {
    alert("Hi, I'm a function expression!");
};
```

As you can see in the above example, the function expression threw an exception when it was invoked before it is defined, but the function declaration executed successfully.

JavaScript parse declaration function before the program executes. Therefore, it doesn't matter if the program invokes the function before it is defined because JavaScript has [hoisted the function](https://www.tutorialrepublic.com/javascript-tutorial/javascript-hoisting.php) to the top of the current scope behind the scenes. The function expression is not evaluated until it is assigned to a variable; therefore, it is still undefined when invoked.

ES6 has introduced even shorter syntax for writing function expression which is called [arrow function](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php#arrow-functions), please check out the [JavaScript ES6 features](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php) chapter to learn more about it.

* * *

## Understanding the Variable Scope

However, you can declare the variables anywhere in JavaScript. But, the location of the declaration determines the extent of a variable's availability within the JavaScript program i.e. where the variable can be used or accessed. This accessibility is known as _variable scope_.

By default, variables declared within a function have _local scope_ that means they cannot be viewed or manipulated from outside of that function, as shown in the example below:

#### Example

```javascript
// Defining function
function greetWorld() {
    var greet = "Hello World!";
    alert(greet);
}
 
greetWorld(); // Outputs: Hello World!
 
alert(greet); // Uncaught ReferenceError: greet is not defined
```

However, any variables declared in a program outside of a function has _global scope_ i.e. it will be available to all script, whether that script is inside a function or outside. Here's an example:

#### Example

```javascript
var greet = "Hello World!";
 
// Defining function
function greetWorld() {
    alert(greet);
}
 
greetWorld();  // Outputs: Hello World!
 
alert(greet); // Outputs: Hello World!
```
* * *