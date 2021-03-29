Closures

# JavaScript Closures

## Understanding the JavaScript Closures

In the [JavaScript functions](https://www.tutorialrepublic.com/javascript-tutorial/javascript-functions.php#variable-scope) chapter you've learnt that in JavaScript a variable's scope can be _global_ or _local_. Since ES6 you can also create [block-scoped variables](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php#let-keyword) using the `let` keyword.

A global variable can be accessed and manipulated anywhere in the program, whereas a local variable can only be accessed and manipulated by the function they are declared in.

However, there are certain situations when you want a variable to be available throughout the script, but you don't want just any part of your code to be able to change its value accidently.

Let's see what happens if you try to achieve this using the global variable:

#### Example

```javascript
// Global variable
var counter  = 0;

// A function dedicated to manipulate the 'counter' variable
function makeCounter() {
    return counter += 1;
}

// Calling the function
makeCounter();
console.log(counter); // Prints: 1

makeCounter();
console.log(counter); // Prints: 2

// Trying to manipulate the 'counter' variable from outside
counter = 10;
console.log(counter); // Prints: 10
```

As you can see in the above example, the value of the `counter` variable can be changed from anywhere in the program, without calling the `makeCounter()` function (_line no-17_).

Now, let's try to achieve the same thing with the local variable and see what happens:

#### Example

```javascript
function makeCounter() {
    // Local variable
    var counter  = 0;
	
    // Manipulating the 'counter' variable
    return counter += 1;
}

// Calling the function
console.log(makeCounter()); // Prints: 1
console.log(makeCounter()); // Prints: 1
```

In this case the `counter` variable cannot be manipulated from outside, since it is local to `makeCounter()` function, but its value will also not increase after subsequent function call, because every time we call the function it reset the `counter` variable value, which you can clearly see in the above example (_line no-11_). The JavaScript closure can solve our problem.

A closure is basically an inner function that has access to the parent function's scope, even after the parent function has finished executing. This is accomplished by creating a function inside another function. Let's take a look at the following example to see how it works:

#### Example

```javascript
function makeCounter() {
    var counter = 0;
	
    // Nested function
    function make() {
        counter += 1;
        return counter;
    }
    return make;
}

/* Execute the makeCounter() function and store the
returned value in the myCounter variable */
var myCounter = makeCounter();

console.log(myCounter()); // Prints: 1
console.log(myCounter()); // Prints: 2
```

As you can see in the above example, the inner function `make()` is returned from the outer function `makeCounter()`. So the value of the `myCounter` is the inner `make()` function (_line no-14_), and calling `myCounter` effectively calls `make()`. In JavaScript functions can assigned to variables, passed as arguments to other functions, can be nested inside other functions, and more.

You'll also notice that the inner function `make()` is still able to access the value of `counter` variable defined in the outer function, even though the `makeCounter()` function has already finished executing (_line no-14_). It happens because functions in JavaScript form closures. Closures internally store references to their _outer variables_, and can access and update their values.

In the example above, the `make()` function is a closure whose code refers to the outer variable `counter`. This implies that whenever the `make()` function is invoked, the code inside it is able to access and update the `counter` variable because it is stored in the closure.

Finally, since the outer function has finished executing, no other part of the code can access or manipulate the `counter` variable. Only the inner function has exclusive access to it.

The previous example can also be written using anonymous function expression, like this:

#### Example

```javascript
// Anonymous function expression
var myCounter = (function() {
    var counter = 0;
	
    // Nested anonymous function
    return function() {
        counter += 1;
        return counter;
    }
})();

console.log(myCounter()); // Prints: 1
console.log(myCounter()); // Prints: 2
```

**Tip:** In JavaScript, all functions have access to the global scope, as well as the scope above them. As JavaScript supports nested functions, this typically means that the nested functions have access to any value declared in a higher scope including its parent function's scope.

**Note:** The global variables live as long as your application (i.e. your web page) lives. Whereas, the local variables have a short life span, they are created when the function is invoked, and destroyed as soon as the function is finished executing.

* * *

## Creating the Getter and Setter Functions

Here we will create a variable `secret` and protect it from being directly manipulated from outside code using closure. We will also create getter and setter functions to get and set its value.

Additionally, the setter function will also perform a quick check whether the specified value is a number or not, and if it is not it will not change the variable value.

#### Example

```javascript
var getValue, setValue;

// Self-executing function
(function() {
    var secret = 0;
    
    // Getter function
    getValue = function() {
        return secret;
    };
    
    // Setter function
    setValue = function(x) {
        if(typeof x === "number") {
            secret = x;
        }
    };
}());

// Calling the functions
getValue(); // Returns: 0
setValue(10);
getValue(); // Returns: 10
setValue(null);
getValue(); // Returns: 10
```

**Tip:** Self-executing functions are also called _immediately invoked function expression (IIFE)_, _immediately executed function_, or _self-executing anonymous function_.

* * *