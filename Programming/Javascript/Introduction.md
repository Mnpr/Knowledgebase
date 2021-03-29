Introduction


# Javascript 

JavaScript is the most popular and widely used client-side scripting language. Client-side scripting refers to scripts that run within your web browser. JavaScript is designed to add interactivity and dynamic effects to the web pages by manipulating the content returned from a web server.

JavaScript was originally developed as LiveScript by Netscape in the mid 1990s. It was later renamed to JavaScript in 1995, and became an ECMA standard in 1997. Now JavaScript is the standard client-side scripting language for web-based applications, and it is supported by virtually all web browsers available today, such as Google Chrome, Mozilla Firefox, Apple Safari, etc.

JavaScript is an object-oriented language, and it also has some similarities in syntax to Java programming language. But, JavaScript is not related to Java in any way.

JavaScript is officially maintained by ECMA (European Computer Manufacturers Association) as ECMAScript. ECMAScript 6 (or ES6) is the latest major version of the ECMAScript standard.

**Tip:** Our JavaScript tutorial will help you to learn the fundamentals of JavaScript scripting language, from the basic to advanced topics step-by-step. If you're a beginner, start with the basics and gradually move forward by learning a little bit every day.

* * *

## What Can be Done with JavaScript

*   Modify the content of a web page by adding or removing elements.
*   Change the style and position of the elements on a web page.
*   Monitor events like mouse click, hover, etc. and react to it.
*   Perform and control transitions and animations.
*   Create alert pop-ups to display info or warning messages to the user.
*   Perform operations based on user inputs and display the results.
*   Validate user inputs before submitting it to the server.

The list does not end here, there are many other interesting things that can be done with JavaScript.

* * *
## Adding JavaScript to HTML Document
* * *
1.   Embedding the JavaScript code between a pair of `<script>` and `</script>` tag.
2.   Creating an external JavaScript file with the `.js` extension and then load it within the page through the `src` attribute of the `<script>` tag.
3.   Placing the JavaScript code directly inside an HTML tag using the special tag attributes such as `onclick`, `onmouseover`, `onkeypress`, `onload`, etc.
* * *
## Embedding the JavaScript Code

JavaScript code can directly be imbeded within  web pages by placing it between the `<script>` and `</script>` tags. The `<script>` tag indicates the browser that the contained statements are to be interpreted as executable script and not HTML.

#### Example

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Embedding JavaScript</title>
</head>
<body>
    <script>
        var greet = "Hello World!";
        document.write(greet);
    </script>
</body>
</html>
```

**Note:** The `type` attribute for `<script>` tag (i.e. `<script type="text/javascript">`) is no longer required since HTML5. JavaScript is the default scripting language for HTML5.

* * *

## Calling an External JavaScript File

You can also place your JavaScript code into a separate file with a `.js` extension, and then call that file in your document through the `src` attribute of the `<script>` tag :
`<script src="js/hello.js"> </script>`

This is useful if you want the same scripts available to multiple documents. It saves you from repeating the same task over and over again, and makes your website much easier to maintain.

#### Example

```
function sayHello() {
    alert("Hello World!");
}

// Call function on click of the button
document.getElementById("myBtn").onclick = sayHello;
```

Now, you can call this external JavaScript file within a web page using the `<script>` tag, like this:

#### Example

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Including External JavaScript File</title>        
</head>
<body>    
    <button type="button" id="myBtn">Click Me</button>
    <script src="js/hello.js"></script>
</body>
</html>
```

**Note:** Usually when an external JavaScript file is downloaded for first time, it is stored in the browser's cache (just like images and style sheets), so it won't need to be downloaded multiple times from the web server that makes the web pages load more quickly.

* * *
## Placing the JavaScript Code Inline

You can also place JavaScript code inline by inserting it directly inside the HTML tag using the special tag attributes such as `onclick`, `onmouseover`, `onkeypress`, `onload`, etc.

However, you should avoid placing large amount of JavaScript code inline as it clutters up your HTML with JavaScript and makes your JavaScript code difficult to maintain. Here's an example:

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Inlining JavaScript</title>        
</head>
<body>    
    <button onclick="alert('Hello World!')">Click Me</button>
</body>
</html>
```

**Tip:** You should always keep the content and structure of your web page (i.e. HTML) separate out from presentation (CSS), and behavior (JavaScript).

* * *

## Positioning of Script inside HTML Document

The `<script>` element can be placed in the `<head>`, or `<body>` section of an HTML document. But ideally, scripts should be placed at the end of the body section, just before the closing `</body>` tag, it will make your web pages load faster, since it prevents obstruction of initial page rendering.

Each `<script>` tag blocks the page rendering process until it has fully downloaded and executed the JavaScript code, so placing them in the head section (i.e. `<head>` element) of the document without any valid reason will significantly impact your website performance.

**Tip:** You can place any number of `<script>` element in a single document. However, they are processed in the order in which they appear in the document, from top to bottom.

* * *

## Difference Between Client-side and Server-side Scripting

Client-side scripting languages such as JavaScript, VBScript, etc. are interpreted and executed by the web browser, while server-side scripting languages such as PHP, ASP, Java, Python, Ruby, etc. runs on the web server and the output sent back to the web browser in HTML format.

Client-side scripting has many advantages over traditional server-side scripting approach. For example, you can use JavaScript to check if the user has entered invalid data in form fields and show notifications for input errors accordingly in real-time before submitting the form to the web-server for final data validation and further processing in order to prevent unnecessary network bandwidth usages and the exploitation of server system resources.

Also, response from a server-side script is slower as compared to a client-side script, because server-side scripts are processed on the remote computer not on the user's local computer.

* * *

# JavaScript Syntax


The syntax of JavaScript is the set of rules that define a correctly structured JavaScript program. A JavaScript consists of JavaScript statements that are placed within the `<script></script>` HTML tags in a web page, or within the external JavaScript file having `.js` extension.

#### Example

```javascript
var x = 5;
var y = 10;
var sum = x + y;
document.write(sum); // Prints variable value
```

* * *

## Case Sensitivity in JavaScript

JavaScript is case-sensitive. This means that variables, language keywords, function names, and other identifiers must always be typed with a consistent capitalization of letters.

* * *

## JavaScript Comments

A comment is simply a line of text that is completely ignored by the JavaScript interpreter. 

* Single-line comments begin with a double forward slash (`//`), followed by the comment text.

* Multi-line comment begins with a slash and an asterisk (`/*`) and ends with an asterisk and slash (`*/`).

#### Example

```javascript
// I am single line comment

/* I am multi
-line comment in JS */

document.write("Hello World!");
```

* * *

## Variables


Variables are fundamental to all programming languages. Variables are used to store data, like string of text, numbers, etc. The data or value stored in the variables can be set, updated, and retrieved whenever needed. In general, variables are symbolic names for values.

You can create a variable with the `var` keyword, whereas the assignment operator (`=`) is used to assign value to a variable, like this: `var varName = value;`

#### Example

```javascript
var name = "Peter Parker";
var age = 21;
var isMarried = false;
```

**Tip:** Always give meaningful names to your variables. Additionally, for naming the variables that contain multiple words, camelCase is commonly used. In this convention all world after the first should have uppercase first letters, e.g. `myLongVariableName`.


Variables can also be declared without having any initial values assigned to them. This is useful for variables which are supposed to hold values like user inputs.

#### Example

```javascript
// Declaring Variable
var userName;
 
// Assigning value
userName = "Clark Kent";
```

**Note:** In JavaScript, if a variable has been declared, but has not been assigned a value explicitly, is automatically assigned the value `undefined`.

* * *

### Declaring Multiple Variables at Once

#### Example

```javascript
// Declaring multiple Variables
var name = "Peter Parker", age = 21, isMarried = false;
 
/* Longer declarations can be written to span
multiple lines to improve the readability */
var name = "Peter Parker",
age = 21,
isMarried = false;

```
* * *
## The let and const Keywords ES6

ES6 introduces two new keywords `let` and `const` for declaring variables.

The `const` keyword works exactly the same as `let`, except that variables declared using `const` keyword cannot be reassigned later in the code.

#### Example

```javascript
// Declaring variables
let name = "Harry Potter";
let age = 11;
let isStudent = true;

// Declaring constant
const PI = 3.14;
console.log(PI); // 3.14

// Trying to reassign
PI = 10; // error
```

Unlike `var`, which declare *function scoped variables* both `let` and `const` keywords declare variables, scoped at block-level (`{}`). Block scoping means that a new scope is created between a pair of curly brackets `{}`. ref : [ES6 Features](:/87ee0e56ebf844c5aea11b62ff866fee).

**Note:** The `let` and `const` keywords are not supported in older browsers like IE10. IE11 support them partially. See the chapter to know how to start using ES6 today.

* * *

## Naming Conventions for JavaScript Variables

*   A variable name must start with a letter, underscore (`_`), or dollar sign (`$`).
*   A variable name cannot start with a number.
*   A variable name can only contain alpha-numeric characters (`A-z`, `0-9`) and underscores.
*   A variable name cannot contain spaces.
*   A variable name cannot be a JavaScript keyword (reserved word)

**Note:** Variable names in JavaScript are case sensitive, it means `$myvar` and `$myVar` are two different variables.

* * *

## JavaScript Generating Output

In JavaScript there are several different ways of generating output including writing output to the browser window or browser console, displaying output in dialog boxes, writing output into an HTML element, etc.
* * *
### Writing Output to Browser Console

You can easily outputs a message or writes data to the browser console using the `console.log()` method. 

#### Example

```javascript
// Printing a simple text message
console.log("Hello World!"); // Prints: Hello World!

// Printing a variable value 
var x = 10;
var y = 20;
var sum = x + y;
console.log(sum); // Prints: 30
```

* * *

### Displaying Output in Alert Dialog Boxes

You can also use alert dialog boxes to display the message or output data to the user. An alert dialog box is created using the `alert()` method. 

#### Example

```javascript
// Displaying a simple text message
alert("Hello World!"); // Outputs: Hello World!

// Displaying a variable value 
var x = 10;
var y = 20;
var sum = x + y;
alert(sum); // Outputs: 30
```

* * *

### Writing Output to the Browser Window

You can use the `document.write()` method to write the content to the current document only while that document is being parsed.

#### Example

```javascript
// Printing a simple text message
document.write("Hello World!"); // Prints: Hello World!

// Printing a variable value 
var x = 10;
var y = 20;
var sum = x + y;
document.write(sum); // Prints: 30
```

If you use the `document.write()` method method after the page has been loaded, it will overwrite all the existing content in that document.

#### Example

```markup
<h1>This is a heading</h1>
<p>This is a paragraph of text.</p>

<button type="button" onclick="document.write('Hello World!')">Click Me</button>
```

* * *

### Inserting Output Inside an HTML Element

You can also write or insert output inside an HTML element using the element's `innerHTML` property. However, before writing the output first we need to select the element using a method such as `getElementById()`.

#### Example

```markup
<p id="greet"></p>
<p id="result"></p>

<script>
// Writing text string inside an element
document.getElementById("greet").innerHTML = "Hello World!";

// Writing a variable value inside an element
var x = 10;
var y = 20;
var sum = x + y;
document.getElementById("result").innerHTML = sum;
</script>
```

Ref:  [Document Object Model](:/bc7b99e9360c4f36993dc93186a11841) manipulation.

<img width="317" height="46" src="../../../../_resources/e63b61b215044ca0a8465bb5d9cd6c0c.svg"/>



