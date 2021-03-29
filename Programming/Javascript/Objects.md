Objects

# JavaScript Objects

In this tutorial you will learn how to create and use objects in JavaScript.

## What is an Object?

JavaScript is an object-based language and in JavaScript almost everything is an object or acts like an object. So, to work with JavaScript effectively and efficiently we need to understand how objects work as well as how to create your own objects and use them.

A JavaScript object is just a collection of named values. These named values are usually referred to as properties of the object. If you remember from the [JavaScript arrays](https://www.tutorialrepublic.com/javascript-tutorial/javascript-arrays.php) chapter, an array is a collection of values, where each value has an index (a numeric key) that starts from zero and increments by one for each value. An object is similar to an array, but the difference is that you define the keys yourself, such as name, age, gender, and so on. In the following sections we'll learn about objects in detail.

## Creating Objects

An object can be created with curly brackets `{}` with an optional list of properties. A property is a "key: value" pair, where the key (or _property name_) is always a string, and value (or _property value_) can be any data type, like strings, numbers, Booleans or complex data type like arrays, functions, and other objects. Additionally, properties with functions as their values are often called methods to distinguish them from other properties. A typical JavaScript object may look like this:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male",
    displayName: function() {
        alert(this.name);
    }
};
```

The above example creates an object called `person` that has three properties `name`, `age`, and `gender` and one method `displayName()`. The `displayName()` method displays the value of `this.name`, which resolves to `person.name`. This is the easiest and preferred way to create a new object in JavaScript, which is known as _object literals_ syntax.

The property names generally do not need to be quoted unless they are reserved words, or if they contain spaces or special characters (anything other than letters, numbers, and the `_` and `$` characters), or if they start with a number, as shown in the following example:

#### Example

```js
var person = {
    "first name": "Peter",
    "current age": 28,
    gender: "Male"
};
```

**Note:** Since ECMAScript 5, reserved words can be used as object's property names without quoting. However, you should avoid doing this for better compatibility.

* * *

## Accessing Object's Properties

To access or get the value of a property, you can use the dot (`.`), or square bracket (`[]`) notation, as demonstrated in the following example:

#### Example

```js
var book = {
    "name": "Harry Potter and the Goblet of Fire",
    "author": "J. K. Rowling",
    "year": 2000
};

// Dot notation
document.write(book.author);  // Prints: J. K. Rowling

// Bracket notation
document.write(book["year"]); // Prints: 2000
```

The dot notation is easier to read and write, but it cannot always be used. If the name of the property is not valid (i.e. if it contains spaces or special characters), you cannot use the dot notation; you'll have to use bracket notation, as shown in the following example:

#### Example

```js
var book = {
    name: "Harry Potter and the Goblet of Fire",
    author: "J. K. Rowling",
    "publication date": "8 July 2000"
};

// Bracket notation
document.write(book["publication date"]); // Prints: 8 July 2000
```

The square bracket notation offers much more flexibility than dot notation. It also allows you to specify property names as variables instead of just string literals, as shown in the example below:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male"
};

var key = prompt("Enter any property name to get its value");
alert(person[key]); // Outputs: Peter (if enter "name")
```

* * *

## Looping Through Object's Properties

You can iterate through the key-value pairs of an object using the `for...in` loop. This loop is specially optimized for iterating over object's properties. Here's an example:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male"
};

// Iterating over object properties
for(var i in person) {  
    document.write(person[i] + "<br>"); // Prints: name, age and gender
}
```

* * *

## Setting Object's Properties

Similarly, you can set the new properties or update the existing one using the dot (`.`) or bracket (`[]`) notation, as demonstrated in the following example:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male"
};

// Setting a new property
person.country = "United States";
document.write(person.country); // Prints: United States

person["email"] = "peterparker@mail.com";
document.write(person.email); // Prints: peterparker@mail.com

// Updating existing property
person.age = 30;
document.write(person.age); // Prints: 30

person["name"] = "Peter Parker";
document.write(person.name); // Prints: Peter Parker
```

* * *

## Deleting Object's Properties

The `delete` operator can be used to completely remove properties from an object. Deleting is the only way to actually remove a property from an object. Setting the property to `undefined` or `null` only changes the value of the property. It does not remove property from the object.

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male",
    displayName: function() {
        alert(this.name);
    }
};

// Deleting property
delete person.age;
alert(person.age); // Outputs: undefined
```

**Note:** The `delete` operator only removes an object property or array element. It has no effect on variables or declared functions. However, you should avoid `delete` operator for deleting an array element, as it doesn't change the array's length, it just leaves a hole in the array.

* * *

## Calling Object's Methods

You can access an object's method the same way as you would access properties—using the dot notation or using the square bracket notation. Here's an example:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male",
    displayName: function() {
        alert(this.name);
    }
};

person.displayName(); // Outputs: Peter
person["displayName"](); // Outputs: Peter
```

* * *

## Manipulating by Value vs. Reference

JavaScript objects are reference types that mean when you make copies of them, you're really just copying the references to that object. Whereas [primitive values](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php) like strings and numbers are assigned or copied as a whole value. To better understand all this, let's check out the following example:

#### Example

```js
var message = "Hello World!";

var greet = message; // Assign message variable to a new variable
greet = "Hi, there!";

document.write(message);  // Prints: Hello World!
document.write(greet);  // Prints: Hi, there!
```

In the above example, we have made a copy of a variable `message` and changed the value of that copy (i.e. variable `greet`). The two variables remain distinct and separate. But, if we do the same thing with an object, we will get a different result, as you see in the following example:

#### Example

```js
var person = {
    name: "Peter",
    age: 28,
    gender: "Male"
};

var user = person; // Assign person variable to a new variable
user.name = "Harry";

document.write(person.name);  // Prints: Harry
document.write(user.name);  // Prints: Harry
```

You can clearly see, any changes made to the variable `user` also change the `person` variable; it happens because both variables reference the same object. So, simply copying the object does not actually clone it but copies the reference to that object.

* * *