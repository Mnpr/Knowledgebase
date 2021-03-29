JSON Parsing

# JavaScript JSON Parsing

Encode and Decode JSON data in JavaScript.

## What is JSON

JSON stands for **J**ava**S**cript **O**bject **N**otation. JSON is extremely lightweight data-interchange format for data exchange between server and client which is quick and easy to parse and generate.

Like XML, JSON is also a text-based format that's easy to write and easy to understand for both humans and computers, but unlike XML, JSON data structures occupy less bandwidth than their XML versions. JSON is based on two basic structures:

*   **Object:** This is defined as an unordered collection of key/value pairs (i.e. `key:value`). Each object begins with a left curly bracket `{` and ends with a right curly bracket `}`. Multiple key/value pairs are separated by a comma `,`.
*   **Array:** This is defined as an ordered list of values. An array begins with a left bracket `[` and ends with a right bracket `]`. Values are separated by a comma `,`.

In JSON, property names or keys are always strings, while the value can be a `**string**`, `**number**`, `**true**` or `**false**`, `**null**` or even an `**object**` or an `**array**`. Strings must be enclosed in double quotes `"` and can contain escape characters such as `\n`, `\t` and `\`. A JSON object may look like this:

#### Example

```javascript
{
    "book": {
        "name": "Harry Potter and the Goblet of Fire",
        "author": "J. K. Rowling",
        "year": 2000,
        "genre": "Fantasy Fiction",
        "bestseller": true
    }
}
```

Whereas an example of JSON array would look something like this:

#### Example

```javascript
{
    "fruits": [
        "Apple",
        "Banana",
        "Strawberry",
        "Mango"
    ]
}
```

**Tip:** A data-interchange format is a text format which is used to interchange or exchange data between different platforms and operating systems. JSON is the most popular and lightweight data-interchange format for web applications.

* * *

## Parsing JSON Data in JavaScript

In JavaScript, you can easily parse JSON data received from the web server using the `JSON.parse()` method. This method parses a JSON string and constructs the JavaScript value or object described by the string. If the given string is not valid JSON, you will get a syntax error.

Let's suppose we've received the following JSON-encoded string from a web server:

#### Example

```javascript
{"name": "Peter", "age": 22, "country": "United States"}
```

Now, we can simply use the JavaScript `JSON.parse()` method to convert this JSON string into a JavaScript object and access individual values using the dot notation (`.`), like this:

#### Example

```javascript
// Store JSON data in a JS variable
var json = '{"name": "Peter", "age": 22, "country": "United States"}';

// Converting JSON-encoded string to JS object
var obj = JSON.parse(json);

// Accessing individual value from JS object
alert(obj.name); // Outputs: Peter
alert(obj.age); // Outputs: 22
alert(obj.country); // Outputs: United States
```

Please check out the tutorial on [PHP JSON parsing](https://www.tutorialrepublic.com/php-tutorial/php-json-parsing.php) to learn, how to return JSON data from a web server in response, as well as, how to encode/decode JSON data on server side using PHP.

* * *

## Parsing Nested JSON Data in JavaScript

JSON objects and arrays can also be nested. A JSON object can arbitrarily contains other JSON objects, arrays, nested arrays, arrays of JSON objects, and so on. The following example will show you how to parse a nested JSON object and extract all the values in JavaScript.

#### Example

```javascript
/* Storing multi-line JSON string in a JS variable
using the new ES6 template literals */
var json = `{
    "book": {
        "name": "Harry Potter and the Goblet of Fire",
        "author": "J. K. Rowling",
        "year": 2000,
        "characters": ["Harry Potter", "Hermione Granger", "Ron Weasley"],
        "genre": "Fantasy Fiction",
        "price": {
            "paperback": "$10.40", "hardcover": "$20.32", "kindle": "$4.11"
        }
    }
}`;

// Converting JSON object to JS object
var obj = JSON.parse(json);

// Define recursive function to print nested values
function printValues(obj) {
    for(var k in obj) {
        if(obj[k] instanceof Object) {
            printValues(obj[k]);
        } else {
            document.write(obj[k] + "<br>");
        };
    }
};

// Printing all the values from the resulting object
printValues(obj);

document.write("<hr>");

// Printing a single value
document.write(obj["book"]["author"] + "<br>");  // Prints: J. K. Rowling
document.write(obj["book"]["characters"][0] + "<br>");  // Prints: Harry Potter
document.write(obj["book"]["price"]["hardcover"]);  // Prints: $20.32
```

* * *

## Encoding Data as JSON in JavaScript

Sometimes JavaScript object or value from your code need to be transferred to the server during an Ajax communication. JavaScript provides `JSON.stringify()` method for this purpose which converts a JavaScript value to a JSON string, as shown below:

### Stringify a JavaScript Object

The following example will show you how to convert a JavaScript object to JSON string:

#### Example

```javascript
// Sample JS object
var obj = {"name": "Peter", "age": 22, "country": "United States"};

// Converting JS object to JSON string
var json = JSON.stringify(obj);
alert(json);
```

The output of the above example will look something like this:

{"name":"Peter","age":22,"country":"United States"}

**Note:** Although, JavaScript and JSON objects look quite similar, but they are not exactly the same. For example, in JavaScript, object property names can be enclosed in single quotes (`'...'`) or double quotes (`"..."`), or you can omit the quotes altogether. But, in JSON, all property names must be enclosed in double quotes.

### Stringify a JavaScript Array

Similarly, you can convert the JavaScript arrays to JSON strings, like this:

#### Example

```javascript
// Sample JS array
var arr = ["Apple", "Banana", "Mango", "Orange", "Papaya"];

// Converting JS array to JSON string
var json = JSON.stringify(arr);
alert(json);
```

The output of the above example will look something like this:

\["Apple","Banana","Mango","Orange","Papaya"\]

**Warning:** Do not use `eval()` function to evaluate JSON data (e.g., including function definitions in JSON string and converting them back into executable functions with `eval()` method), as it allows attacker to inject malicious JavaScript code into your application.

* * *