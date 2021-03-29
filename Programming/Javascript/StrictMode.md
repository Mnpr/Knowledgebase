Strict Mode

# JavaScript Strict Mode

In this tutorial you will learn how to execute your code in strict mode in JavaScript.

## What is Strict Mode

The _strict mode_ was introduced in ECMAScript 5 (ES5). It is a semantically stricter or restricted version of JavaScript language that produces errors for those mistakes that are handled silently otherwise. For example, in _non-strict_ mode if you initialize a variable without declaring it using the `var` keyword (e.g. `x = 5;`), JavaScript interpreter will assume that you were referring to a global variable and if no such variable existed, it will automatically create one.

Also, features that are deprecated may also generate errors in strict mode. Hence, strict mode reduces bugs, improves security and overall performance of your application.
* * *
## Enabling Strict Mode

To enable strict mode all you need to do is just add the string `"use strict"` at the beginning of your script, as shown in the following example:

#### Example

```javascript
"use strict";

// All your code goes here
x = 5; // ReferenceError: x is not defined
console.log(x);
```

If you add the `"use strict"` directive as the first line of your JavaScript program, strict mode applies to the entire script. But, you can also turn on strict mode only within a function, like this:

#### Example

```javascript
x = 5;
console.log(x); // 5

function sayHello() {
    "use strict";
    str = "Hello World!"; // ReferenceError: str is not defined
    console.log(str);
}
sayHello();
```

**Note:** The `"use strict"` directive is only recognized at the beginning of a script or a function. All modern browsers support `"use strict"` directive except Internet Explorer 9 and lower versions. Additionally, the browsers that don't support the `"use strict"` directive silently ignore it and parse the JavaScript in non-strict mode.

* * *

## General Restrictions in Strict Mode

Strict mode changes both syntax and runtime behavior. In the following sections, we will look at the general restrictions that are enforced in the strict mode:

### Undeclared Variables are Not Allowed

As you already know, in strict mode, all variables must be declared. if you assign a value to an identifier that is not a declared variable, a ReferenceError will be thrown.

#### Example

```javascript
"use strict";

function doSomething() {
    msg = "Hi, there!"; // ReferenceError: msg is not defined
    return msg;
}
console.log(doSomething());
```

### Deleting a Variable or a Function is Not Allowed

In strict mode, if you try to delete a variable or a function, a syntax error will be thrown. Whereas, in non-strict mode, such attempt fails silently and the delete expression evaluates to `false`.

#### Example

```javascript
"use strict";

var person = {name: "Peter", age: 28};
delete person; // SyntaxError
```

Similarly, when you try to delete a function in strict mode you will get an syntax error:

#### Example

```javascript
"use strict";

function sum(a, b) {
    return a + b;
}
delete sum; // SyntaxError
```

### Duplicating a Parameter Name is Not Allowed

In strict mode, a syntax error will be thrown, if a function declaration has two or more parameters with the same name. In non-strict mode, no error occurs.

#### Example

```javascript
"use strict";

function square(a, a) { // SyntaxError
    return a * a;
}
console.log(square(2, 2));
```

### The eval Method Cannot Alter Scope

In strict mode, for security reasons, code passed to `eval()` cannot declare/modify variables or define functions in the surrounding scope as it can in non-strict mode.

#### Example

```javascript
"use strict";

eval("var x = 5;");
console.log(x); // ReferenceError: x is not defined
```

### The eval and arguments Cannot be Used as Identifiers

In strict mode, the names `eval` and `arguments` are treated like keywords, so they cannot be used as variable names, function names, or as function parameter names, etc.

#### Example

```javascript
"use strict";

var eval = 10; // SyntaxError
console.log(eval);
```

### The with Statement is Not Allowed

In strict mode, the `with` statement is not allowed. The `with` statement adds the properties and methods of the [object](https://www.tutorialrepublic.com/javascript-tutorial/javascript-objects.php) to the current scope. So, the statements nested inside the `with` statement can call the properties and methods of the object directly without referring it.

#### Example

```javascript
"use strict";

// Without with statement
var radius1 = 5;
var area1 = Math.PI * radius1 * radius1;

// Using with statement
var radius2 = 5;
with(Math) { // SyntaxError
    var area2 = PI * radius2 * radius2;
} 
```

### Writing to a Read-only Property is Not Allowed

In strict mode, assigning value to a non-writable property, a get-only property or a non-existing property will throw an error. In non-strict mode, these attempts fail silently.

#### Example

```javascript
"use strict";

var person = {name: "Peter", age: 28};

Object.defineProperty(person, "gender", {value: "male", writable: false});
person.gender = "female"; // TypeError
```

### Adding a New Property to a Non-extensible Object is Not Allowed

In strict mode, attempts to create new properties on non-extensible or non-existing objects will also throw an error. But in non-strict mode, these attempts fail silently.

#### Example

```javascript
"use strict";

var person = {name: "Peter", age: 28};

console.log(Object.isExtensible(person)); // true
Object.freeze(person); // lock down the person object
console.log(Object.isExtensible(person)); // false
person.gender = "male"; // TypeError
```

### Octal Numbers are Not Allowed

In strict mode, octal numbers (numbers prefixed with a zero e.g. 010, 0377) are not allowed. Though, it is supported in all browsers in non-strict mode. However, in ES6 octal numbers are supported by prefixing a number with `0o` i.e. 0o10, 0o377, etc.

#### Example

```javascript
"use strict";

var x = 010; // SyntaxError
console.log(parseInt(x));
```

You can clearly see in the above examples how strict mode can help you prevent making common mistakes that often go unnoticed while writing a JavaScript program.

### Keywords Reserved for Future are Not Allowed

As you already know from the previous chapters, the _reserved words_ cannot be used as identifier (variable names, function names, and loop labels) in a JavaScript program. In addition to that the strict mode also imposes restrictions on uses of those keywords that are reserved for future.

As per the latest ECMAScript 6 (or ES6) standards, these keywords are reserved keywords when they are found in strict mode code: `await`, `implements`, `interface`, `package`, `private`, `protected`, `public`, and `static`. However, for optimal compatibility you should avoid using the reserved keywords as variable names or function names in your program.

**Tip:** Reserved words, which are also called keywords, are special words that are part of the JavaScript language syntax, for example, `var`, `if`, `for`, `function`, etc. See the [JS reserved keywords reference](https://www.tutorialrepublic.com/javascript-reference/javascript-reserved-keywords.php) for a complete list of all reserved words in JavaScript.

* * *