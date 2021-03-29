Borrowing Methods

# Borrowing Methods

In this tutorial you will learn how to borrow functionality from existing objects in JavaScript.

## Borrowing Methods from Objects

In JavaScript, you can borrow methods from other objects to build some functionality without inheriting all their properties and methods.

JavaScript provides two methods for all function objects, `call()` and `apply()`, that allow a function to be invoked as if it were a method of another object. Here's an example:

#### Example

```javascript
var objA = {
    name: "object A",
    say: function(greet) {
        alert(greet + ", " + this.name);
    }
}

objA.say("Hi"); // Displays: Hi, object A

var objB = {
    name: "object B"
}

/* The objA doesn't have say() method, but it can borrow it from objA */
objA.say.call(objB, "Hello"); // Displays: Hello, object B
```

* * *

## Difference Between `call()` and `apply()` Methods

The syntax of the `apply()` method is almost identical to `call()`, the only difference is, the `call()` method takes a list of arguments like `call(_thisObj_, _arg1_, _arg2_, ...)`, while the `apply()` method takes a single array of arguments like `apply(_thisObj_, [_argsArray_])`.

Notice the square brackets (`[]`), which denotes an array, in the last line of the following example:

#### Example

```javascript
var objA = {
    name: "object A",
    say: function(greet) {
        alert(greet + ", " + this.name);
    }
}

objA.say("Hi"); // Displays: Hi, object A

var objB = {
    name: "object B"
}

/* The objA doesn't have say() method, but it can borrow it from objA */
objA.say.apply(objB, ["Hello"]); // Displays: Hello, object B
```

* * *

## Using Built-in Methods

The `apply()` method also allows you to use built-in methods for performing some tasks quickly and easily. One such example is using the `Math.max()`/`Math.min()` to find out the maximum or minimum value in an array, that would otherwise require looping over the array values.

As you already know from the previous chapters JavaScript arrays do not have a `max()` method, but [Math](https://www.tutorialrepublic.com/javascript-tutorial/javascript-math-operations.php) has, so we can apply the `Math.max()` method, like this:

#### Example

```javascript
var numbers = [2, 5, 6, 4, 3, 7];

// Using Math.max apply
var max = Math.max.apply(null, numbers);
alert(max); // Outputs: 7
```

**Note:** The first argument to both `call()` and `apply()` is the object on which the function is to be invoked. Using `null` as the first argument is like calling the function without providing any object for the `this` pointer inside the function.

The new ES6 [spread operator](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php#spread-operator) provides a shorter way to obtain the maximum or minimum value from an array without using the `apply()` method. Here's an example:

#### Example

```javascript
var numbers = [2, 5, 6, 4, 3, 7];

// Using spread operator
var max = Math.max(...numbers);
alert(max); // Outputs: 7
```

However, both spread (`...`) and `apply()` will either fail or return the incorrect result if the array has too many elements (e.g. tens of thousands). In that case you can use the `Array.reduce()` to find the maximum or minimum value in a numeric array, by comparing each value, like this:

#### Example

```javascript
var numbers = [2, 5, 6, 4, 3, 7,11,3,4,55,66,75,23,43,55,34,21,22];
var max = numbers.reduce((a,b) => Math.max(a,b));
alert(max);

```
* * *