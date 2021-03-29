Loops

# Loops

In this tutorial you will learn how to repeat a series of actions using loops in JavaScript.

## Different Types of Loops in JavaScript

Loops are used to execute the same block of code again and again, as long as a certain condition is met. The basic idea behind a loop is to automate the repetitive tasks within a program to save the time and effort. JavaScript now supports five different types of loops:

*   **while** — loops through a block of code as long as the condition specified evaluates to true.
*   **do…while** — loops through a block of code once; then the condition is evaluated. If the condition is true, the statement is repeated as long as the specified condition is true.
*   **for** — loops through a block of code until the counter reaches a specified number.
*   **for…in** — loops through the properties of an object.
*   **for…of** — loops over iterable objects such as arrays, strings, etc.

In the following sections, we will discuss each of these loop statements in detail.

* * *

## The while Loop

This is the simplest looping statement provided by JavaScript.

The `while` loop loops through a block of code as long as the specified condition evaluates to true. As soon as the condition fails, the loop is stopped. The generic syntax of the while loop is:
```
while(_condition_) {  
    _// Code to be executed_  
}
```
The following example defines a loop that will continue to run as long as the variable `i` is less than or equal to 5. The variable `i` will increase by 1 each time the loop runs:

#### Example

```javascript
var i = 1;
while(i <= 5) {    
    document.write("<p>The number is " + i + "</p>");
    i++;
}
```

**Note:** Make sure that the condition specified in your loop eventually goes false. Otherwise, the loop will never stop iterating which is known as infinite loop. A common mistake is to forget to increment the counter variable (variable `i` in our case).

* * *

## The do...while Loop

The `do-while` loop is a variant of the `while` loop, which evaluates the condition at the end of each loop iteration. With a `do-while` loop the block of code executed once, and then the condition is evaluated, if the condition is true, the statement is repeated as long as the specified condition evaluated to is true. The generic syntax of the do-while loop is:
```
do {  
    _// Code to be executed_  
}  
while(_condition_);
```
The JavaScript code in the following example defines a loop that starts with `i=1`. It will then print the output and increase the value of variable `i` by 1. After that the condition is evaluated, and the loop will continue to run as long as the variable `i` is less than, or equal to 5.

#### Example

```javascript
var i = 1;
do {
    document.write("<p>The number is " + i + "</p>");
    i++;
}
while(i <= 5);
```

## Difference Between while and do...while Loop

The `while` loop differs from the `do-while` loop in one important way — with a `while` loop, the condition to be evaluated is tested at the beginning of each loop iteration, so if the conditional expression evaluates to false, the loop will never be executed.

With a `do-while` loop, on the other hand, the loop will always be executed once even if the conditional expression evaluates to false, because unlike the `while` loop, the condition is evaluated at the end of the loop iteration rather than the beginning.

* * *

## The for Loop

The `for` loop repeats a block of code as long as a certain condition is met. It is typically used to execute a block of code for certain number of times. Its syntax is:
```
for(_initialization_; _condition_; _increment_) {  
    _// Code to be executed_  
}
```
The parameters of the `for` loop statement have following meanings:

*   **_initialization_** -- it is used to initialize the counter variables, and evaluated once unconditionally before the first execution of the body of the loop.
*   **_condition_** -- it is evaluated at the beginning of each iteration. If it evaluates to `true`, the loop statements execute. If it evaluates to `false`, the execution of the loop ends.
*   **_increment_** -- it updates the loop counter with a new value each time the loop runs.

The following example defines a loop that starts with `i=1`. The loop will continued until the value of variable `i` is less than or equal to 5. The variable `i` will increase by 1 each time the loop runs:

#### Example

```javascript
for(var i=1; i<=5; i++) {
    document.write("<p>The number is " + i + "</p>");
}
```

The `for` loop is particularly useful for iterating over an array. The following example will show you how to print each item or element of the JavaScript  [Arrays](:/19438d8a4a964c0ea3f9e5a662c2e646)

#### Example

```javascript
// An array with some elements
var fruits = ["Apple", "Banana", "Mango", "Orange", "Papaya"];
 
// Loop through all the elements in the array 
for(var i=0; i<fruits.length; i++) {
    document.write("<p>" + fruits[i] + "</p>");
}
```

* * *

## The for...in Loop

The `for-in` loop is a special type of a loop that iterates over the properties of an [object](https://www.tutorialrepublic.com/javascript-tutorial/javascript-objects.php), or the elements of an array. The generic syntax of the `for-in` loop is:
```
for(_variable_ in _object_) {  
    _// Code to be executed_  
}
```
The loop counter i.e. _variable_ in the `for-in` loop is a string, not a number. It contains the name of current property or the index of the current array element.

The following example will show you how to loop through all properties of a JavaScript object.

#### Example

```javascript
// An object with some properties 
var person = {"name": "Clark", "surname": "Kent", "age": "36"};
 
// Loop through all the properties in the object  
for(var prop in person) {  
    document.write("<p>" + prop + " = " + person[prop] + "</p>"); 
}
```

Similarly, you can loop through the elements of an array, like this:

#### Example

```javascript
// An array with some elements
var fruits = ["Apple", "Banana", "Mango", "Orange", "Papaya"];
 
// Loop through all the elements in the array 
for(var i in fruits) {  
    document.write("<p>" + fruits[i] + "</p>");
}
```

**Note:** The `for-in` loop should not be used to iterate over an array where the index order is important. You should better use a `for` loop with a numeric index.

* * *

## The for...of Loop ES6

ES6 introduces a new `for-of` loop which allows us to iterate over [arrays](https://www.tutorialrepublic.com/javascript-tutorial/javascript-arrays.php) or other iterable objects (e.g. [strings](https://www.tutorialrepublic.com/javascript-tutorial/javascript-strings.php)) very easily. Also, the code inside the loop is executed for each element of the iterable object.

The following example will show you how to loop through arrays and strings using this loop.

#### Example

```javascript
// Iterating over array
let letters = ["a", "b", "c", "d", "e", "f"];

for(let letter of letters) {
    console.log(letter); // a,b,c,d,e,f
}

// Iterating over string
let greet = "Hello World!";

for(let character of greet) {
    console.log(character); // H,e,l,l,o, ,W,o,r,l,d,!
}
```

**Note:** The `for...of` loop doesn't work with objects because they are not iterable. If you want to iterate over the properties of an object you can use the [`for-in`](https://www.tutorialrepublic.com/javascript-tutorial/javascript-loops.php#for-in) loop.

* * *