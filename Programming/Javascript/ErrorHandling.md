Error Handling

# JavaScript Error Handling

## Handling Errors

Sometimes your JavaScript code does not run as smooth as expected, resulting in an error. There are a number of reasons that may cause errors, for instance:

*   A problem with network connection
*   A user might have entered an invalid value in a form field
*   Referncing objects or functions that do not exist
*   Incorrect data being sent to or received from the web server
*   A service that the application needs to access might be temporarily unavailable

These types of errors are known as runtime errors, because they occur at the time the script runs. A professional application must have the capabilities to handle such runtime error gracefully. Usually this means informing the user about the problem more clearly and precisely.
* * *
## The try...catch Statement

JavaScript provides the `try-catch` statement to trap the runtime errors, and handle them gracefully.

Any code that might possibly throw an error should be placed in the `try` block of the statement, and the code to handle the error is placed in the `catch` block, as shown here:
```
try {  
    _// Code that may cause an error_  
} catch(error) {  
    _// Action to be performed when an error occurs_  
}
```
If an error occurs at any point in the `try` block, code execution immediately transferred from the `try` block to the `catch` block. If no error occurs in the `try` block, the `catch` block will be ignored, and the program will continue executing after the `try-catch` statement.

The following example demonstrates how the `try-catch` statement actually works:

#### Example

```javascript
try {
    var greet = "Hi, there!";
    document.write(greet);
    
    // Trying to access a non-existent variable
    document.write(welcome);
    
    // If error occurred following line won't execute
    alert("All statements are executed successfully.");
} catch(error) {
    // Handle the error
  alert("Caught error: " + error.message);
}
 
// Continue execution
document.write("<p>Hello World!</p>");
```

The above script will generate an error that is displayed in an alert dialog box, instead of printing it to browser console. Besides that, the program didn't stop abruptly even though an error has occurred.

Also, note that the `catch` keyword is followed by an identifier in parentheses. This identifier is act like a function parameter. When an error occurs, the JavaScript interpreter generates an object containing the details about it. This error object is then passed as an argument to `catch` for handling.

**Tip:** The `try-catch` statement is an exception handling mechanism. An exception is signal that indicates that some sort of exceptional condition or error has occurred during the execution of a program. The terms "exception" and "error" are often used interchangeably.

* * *

## The try...catch...finally Statement

The `try-catch` statement can also have a `finally` clause. The code inside the `finally` block will always execute, regardless of whether an error has occurred in the `try` block or not.

The following example will always display the total time taken to complete the execution of the code.

#### Example

```javascript
// Assigning the value returned by the prompt dialog box to a variable
var num = prompt("Enter a positive integer between 0 to 100");

// Storing the time when execution start
var start = Date.now();

try {
    if(num > 0 && num <= 100) {
        alert(Math.pow(num, num)); // the base to the exponent power
    } else {
        throw new Error("An invalid value is entered!");
    }
} catch(e) {
    alert(e.message);
} finally {
    // Displaying the time taken to execute the code
    alert("Execution took: " + (Date.now() - start) + "ms");
}
```

* * *

## Throwing Errors

So far we've seen the errors that are automatically thrown by JavaScript parser when an error occurs. However, it is also possible to throw an error manually by using the `throw` statement.

The general form (or syntax) of the `throw` statement is: `throw _expression_;`

The `_expression_` can be a object or a value of any data type. However, it's better to use the objects, preferably with `name` and `message` properties. The JavaScript built-in `Error()` constructor provides a convenient way create an error object. Let's look at some examples:

#### Example

```javascript
throw 123;
throw "Missing values!";
throw true;
throw { name: "InvalidParameter", message: "Parameter is not a number!" };
throw new Error("Something went wrong!");
```

**Note:** If you're using the JavaScript built-in error constructor functions (e.g. `Error()`, `TypeError()`, etc.) for creating error objects, then the `name` property is same as the name of the constructor, and the `message` is equal to the argument passed to the constructor function.

Now we're going to create a function `squareRoot()` to find the square root of a number. This can be done simply by using the JavaScript built-in function `Math.sqrt()`, but the problem here is, it returns `NaN` for negative numbers, without providing any hint on what has gone wrong.

We're going to fix this problem by throwing a custom error if a negative number is supplied.

#### Example

```javascript
function squareRoot(number) {
    // Throw error if number is negative
    if(number < 0) {
        throw new Error("Sorry, can't calculate square root of a negative number.");
    } else {
        return Math.sqrt(number);
    }
}
    
try {
    squareRoot(16);
    squareRoot(625);
    squareRoot(-9);
    squareRoot(100);
    
    // If error is thrown following line won't execute
    alert("All calculations are performed successfully.");
} catch(e) {
    // Handle the error
    alert(e.message);
}
```

**Tip:** Theoretically it is possible to calculate the square root of negative number by using the imaginary number `_i_`, where `_i_2 = -1`. Therefore square root of `-4` is `2i`, square root of `-9` is `3i`, and so on. But imaginary numbers are not supported in JavaScript.

* * *

## Error Types

The `Error` object is the base type of all errors and it has two main properties — a `name` property that specifies the _type of error_, and a `message` property that holds a message describing the error in more detail. Any error thrown will be an instance of the `Error` object.

There are several different types of error that can occur during the execution of a JavaScript program, such as `RangeError`, `ReferenceError`, `SyntaxError`, `TypeError`, and `URIError`.

The following section describes each one of these error type in more detail:
* * *
## RangeError

A `RangeError` is thrown when you use a number that is outside the range of allowable values. For example, creating an array with a negative length will throw `RangeError`.

#### Example

```javascript
var num = 12.735;
num.toFixed(200); // throws a range error (allowable range from 0 to 100)

var array = new Array(-1); // throws a range error
```
* * *
## ReferenceError

A `ReferenceError` is typically thrown when you try to reference or access a variable or object that doesn't exist. The following example shows how the `ReferenceError` occurs.

#### Example

```javascript
var firstName = "Harry";
console.log(firstname); // throws a reference error (variable names are case-sensitive)

undefinedObj.getValues(); // throws a reference error

nonexistentArray.length; // throws a reference error
```
* * *
## SyntaxError

A `SyntaxError` is thrown at runtime if there is any syntax problem in your JavaScript code. For example, if closing bracket is missing, loops are not structured properly, and so on.

#### Example

```javascript
var array = ["a", "b", "c"];
document.write(array.slice(2); // throws a syntax error (missing bracket)

alert("Hello World!'); // throws a syntax error (quote mismatch)
```
* * *
## TypeError

A `TypeError` is thrown when a value is not of the expected type. For example, calling a string method on number, calling an array method on string, and so on.

#### Example

```javascript
var num = 123;
num.toLowerCase(); /* throws a type error (since toLowerCase() is a string method, a number can't be converted to lowercase) */

var greet = "Hello World!"
greet.join() // throws a type error (since join() is an array method)
```
* * *
## URIError

A `URIError` is thrown when you specified an invalid URI (_stands for_ Uniform Resource Identifier) to the URI-related functions such as `encodeURI()` or `decodeURI()`, as shown here:

#### Example

```javascript
var a = "%E6%A2%B";
decodeURI(a);  // throws a URI error

var b = "\uD800";
encodeURI(b);   // throws a URI error
```

**Note:** There is one more error type `EvalError` which is thrown when an error occurs during the execution of code via `eval()` function. But, this error is not thrown by JavaScript anymore, however this object still remains for backward compatibility.

The specific error type can also be thrown manually using their respective constructor and the `throw` statement, e.g., to throw a `TypeError` you can use the `TypeError()` constructor, like this:

#### Example

```javascript
var num = prompt("Please enter a number");

try {
    if(num != "" && num !== null && isFinite(+num)) {
        alert(Math.exp(num));
    } else {
        throw new TypeError("You have not entered a number.");
    }
} catch(e) {
    alert(e.name);
    alert(e.message);
    alert(e.stack); // non-standard property
}
```

**Note:** The `Error` object also supports some non-standard properties. One of the most widely used such property is: `stack`, which returns the _stack trace_ for that error. You can use it for debugging purposes, but don't use it on production sites.

* * *