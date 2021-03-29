## Data Types in JavaScript

There are six basic data types in JavaScript which can be divided into three main categories: primitive (or _primary_), _composite_ (or _reference_), and 
_special_ data types. String, Number, and Boolean are primitive data types. Object, Array, and Function (which are all types of objects) are composite data types. Whereas Undefined and Null are special data types.

Primitive data types can hold only one value at a time, whereas composite data types can hold collections of values and more complex entities. Let's discuss each one of them in detail.

* * *

## String

* * *

### String Type

The `string` data type is used to represent textual data (i.e. sequences of characters). Strings are created using single or double quotes surrounding one or more characters:

* * *

A string is a sequence of letters, numbers, special characters and arithmetic values or combination of all. Strings can be created by enclosing the string literal (i.e. string characters) either within single quotes (`'`) or double quotes (`"`),

#### Example

```javascript
var myString = 'Hello World!'; // Single quoted string
var myString = "Hello World!"; // Double quoted string
```

You can use quotes inside a string, as long as they don't match the quotes surrounding the string:

#### Example

```javascript
var str1 = "it's okay";
var str2 = 'He said "Goodbye"';
var str3 = "She replied 'Calm down, please'";
var str4 = 'Hi, there!"; // Syntax error - quotes must match
```

However, you can still use single quotes inside a single quoted strings or double quotes inside double quoted strings by escaping the quotes with a backslash character (`\`), like this:

#### Example

```javascript
var str1 = 'it\'s okay';
var str2 = "He said \"Goodbye\"";
var str3 = 'She replied \'Calm down, please\'';
```

The backslash (`\`) is called an escape character, whereas the sequences `\'` and `\"` that we've used in the example above are called `escape sequences`.

* * *

## JavaScript Escape Sequences

Escape sequences are also useful for situations where you want to use characters that can't be typed using a keyboard. Here are some other most commonly used escape sequences.

* `\n` is replaced by the newline character
* `\t` is replaced by the tab character
* `\r` is replaced by the carriage-return character
* `\b` is replaced by the backspace character
* `\\` is replaced by a single backslash (`\`)

Here's an example to clarify the how escape sequences actually works:

#### Example

```javascript
var str1 = "The quick brown fox \n jumps over the lazy dog.";
document.write("<pre>" + str1 + "</pre>"); // Create line break

var str2 = "C:\Users\Downloads";
document.write(str2); // Prints C:UsersDownloads

var str3 = "C:\\Users\\Downloads";
document.write(str3); // Prints C:\Users\Downloads
```

* * *

## Operations on Strings

JavaScript provides several properties and methods to perform operations on string values. Technically, only objects can have properties and methods. But in JavaScript primitive data types can act like objects when you refer to them with the property access notation (i.e. dot notation).

JavaScript is making it possible by creating a temporary wrapper object for primitive data types. This process is done automatically by the JavaScript interpreter in the background.

***

### Getting the Length of a String

The length property returns the length of the string, which is the number of characters contained in the string. This includes the number of special characters as well, such as `\t` or `\n`.

#### Example

```javascript
var str1 = "This is a paragraph of text.";
document.write(str1.length); // Prints 28

var str2 = "This is a \n paragraph of text.";
document.write(str2.length); // Prints 30, because \n is only one character
```

**Note:** Since `length` is a property, not a function, so don't use parentheses after it like `str.length()`. Instead just write `str.length`, otherwise it will produce an error.

* * *

### Finding a String Inside Another String

You can use the `indexOf()` method to find a substring or string within another string. This method returns the index or position of the first occurrence of a specified string within a string.

#### Example

```javascript
var str = "If the facts don't fit the theory, change the facts.";
var pos = str.indexOf("facts");
alert(pos); // 0utputs: 7
```

Similarly, use the `lastIndexOf()` method to get the index or position of the last occurrence of the specified string within a string :

#### Example

```javascript
var str = "If the facts don't fit the theory, change the facts.";
var pos = str.lastIndexOf("facts");
alert(pos); // 0utputs: 46
```

Both the `indexOf()`, and the `lastIndexOf()` methods return `-1` if the substring is not found. Both methods also accept an optional integer parameter which specifies the position within the string at which to start the search. Here's an example:

#### Example

```javascript
var str = "If the facts don't fit the theory, change the facts.";

// Searching forwards
var pos1 = str.indexOf("facts", 20);
alert(pos1); // 0utputs: 46

// Searching backwards
var pos2 = str.lastIndexOf("facts", 20);
alert(pos2); // 0utputs: 7
```

**Note:** Characters in a string are indexed from left to right. The index of the first character is `0`, and the index of the last character of a string called `myStr` is `myStr.length - 1`.

* * *

### Searching for a Pattern Inside a String

You can use the `search()` method to search a particular piece of text or pattern inside a string.

Like `indexOf()` method the `search()` method also returns the index of the first match, and returns `-1` if no matches were found, but unlike `indexOf()` method this method can also take a _regular expression_ as its argument to provide advanced search capabilities.

#### Example

```javascript
var str = "Color red looks brighter than color blue.";

// Case sensitive search
var pos1 = str.search("color");
alert(pos1); // 0utputs: 30

// Case insensitive search using regexp
var pos2 = str.search(/color/i);
alert(pos2); // 0utputs: 0
```

**Note:** The `search()` method does not support global searches; it ignores the `g` flag or modifier (i.e. `/pattern/g`) of its regular expression argument.

Ref: [Regular Expressions](:/4655f47fb00d4af58e2c03abfff0734d)

* * *

### Extracting a Substring from a String

You can use the `slice()` method to extract a part or substring from a string.

This method takes 2 parameters: _start index_ (index at which to begin extraction), and an optional _end index_ (index before which to end extraction), like `str.slice(startIndex, endIndex)`.

#### Example

```javascript
var str = "The quick brown fox jumps over the lazy dog.";
var subStr = str.slice(4, 15);
document.write(subStr); // Prints: quick brown
```

You can also specify negative values. The negative value is treated as `strLength + startIndex`, where `strLength` is the length of the string (i.e. `str.length`), for example, if `startIndex` is `-5` it is treated as `strLength - 5`. If `startIndex` is greater than or equal to the length of the string, `slice()` method returns an empty string. Also, if optional `endIndex` is not specified or omitted, the `slice()` method extracts to the end of the string.

#### Example

```javascript
var str = "The quick brown fox jumps over the lazy dog.";
document.write(str.slice(-28, -19)); // Prints: fox jumps
document.write(str.slice(31)); // Prints: the lazy dog.
```

You can also use the `substring()` method to extract a section of the given string based on start and end indexes, like `str.substring(startIndex, endIndex)`. The `substring()` method is very similar to the `slice()` method, except few differences:

* If either argument is less than `0` or is `NaN`, it is treated as `0`.
* If either argument is greater than `str.length`, it is treated as if it were `str.length`.
* If `startIndex` is greater than `endIndex`, then `substring()` will swap those two arguments; for example, `str.substring(5, 0) == str.substring(0, 5)`.

The following example will show you how this method actuallty works:

#### Example

```javascript
var str = "The quick brown fox jumps over the lazy dog.";
document.write(str.substring(4, 15)); // Prints: quick brown
document.write(str.substring(9, 0)); // Prints: The quick
document.write(str.substring(-28, -19)); // Prints nothing
document.write(str.substring(31)); // Prints: the lazy dog.
```

* * *

### Extracting a Fixed Number of Characters from a String

JavaScript also provide the `substr()` method which is similar to `slice()` with a subtle difference, the second parameter specifies the number of characters to extract instead of ending index, like `str.substr(startIndex, length)`. If `length` is `0` or a negative number, an empty string is returned.

#### Example

```javascript
var str = "The quick brown fox jumps over the lazy dog.";
document.write(str.substr(4, 15)); // Prints: quick brown fox
document.write(str.substr(-28, -19)); // Prints nothing
document.write(str.substr(-28, 9)); // Prints: fox jumps
document.write(str.substr(31)); // Prints: the lazy dog.
```

* * *

### Replacing the Contents of a String

You can use the `replace()` method to replace part of a string with another string. This method takes two parameters a regular expression to match or substring to be replaced and a replacement string, like `str.replace(regexp|substr, newSubstr)`.

This `replace()` method returns a new string, it doesn't affect the original string that will remain unchanged.

#### Example

```javascript
var str = "Color red looks brighter than color blue.";
var result = str.replace("color", "paint");
alert(result); // 0utputs: Color red looks brighter than paint blue.
```

By default, the `replace()` method replaces only the first match, and it is case-sensitive. To replace the substring within a string in a case-insensitive manner you can use a _regular expression (regexp)_ with an `i` modifier, as shown in the example below:

#### Example

```javascript
var str = "Color red looks brighter than color blue.";
var result = str.replace(/color/i, "paint");
alert(result); // 0utputs: paint red looks brighter than color blue.
```

Similarly, to replace all the occurrences of a substring within a string in a case-insensitive manner you can use the `g` modifier along with the `i` modifier, like this:

#### Example

```javascript
var str = "Color red looks brighter than color blue.";
var result = str.replace(/color/ig, "paint");
alert(result); // 0utputs: paint red looks brighter than paint blue.
```

* * *

### Converting a String to Uppercase or Lowercase

You can use the `toUpperCase()` method to convert a string to uppercase, like this:

#### Example

```javascript
var str = "Hello World!";
var result = str.toUpperCase();
document.write(result); // Prints: HELLO WORLD!
```

Similarly, you can use the `toLowerCase()` to convert a string to lowercase, like this:

#### Example

```javascript
var str = "Hello World!";
var result = str.toLowerCase();
document.write(result); // Prints: hello world!
```

* * *

### Concatenating Two or More Strings

#### Example

```javascript
var hello = "Hello";
var world = "World";
var greet = hello + " " + world;
document.write(greet); // Prints: Hello World

var wish  = "Happy";
    wish += " New Year";
document.write(wish); // Prints: Happy New Year
```

JavaScript also provides `concat()` method to combine strings, but it is not recommended.

* * *

### Accessing Individual Characters from a String

You can use the `charAt()` method to access individual character from a string, like `str.charAt(index)`. The `index` specified should be an integer between `0` and `str.length - 1`. If no index is provided the first character in the string is returned, since the default is `0`.

#### Example

```javascript
var str = "Hello World!";
document.write(str.charAt());  // Prints: H
document.write(str.charAt(6)); // Prints: W
document.write(str.charAt(30)); // Prints nothing
document.write(str.charAt(str.length - 1)); // Prints: !
```

There is even better way to do this. Since ECMAScript 5, strings can be treated like read-only arrays, and you can access individual characters from a string using square brackets (`[]`) instead of the `charAt()` method, as demonstrated in the following example:

#### Example

```javascript
var str = "Hello World!";
document.write(str[0]); // Prints: H
document.write(str[6]); // Prints: W
document.write(str[str.length - 1]); // Prints: !
document.write(str[30]); // Prints: undefined
```

**Note:** The only difference between accessing the character from a string using the `charAt()` and square bracket (`[]`) is that if no character is found, `[]` returns [`undefined`](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php#undefined), whereas the `charAt()` method returns an empty string.

* * *

### Splitting a String into an Array

The `split()` method can be used to splits a string into an array of strings, using the syntax `str.split(separator, limit)`. The `seperator` argument specifies the string at which each split should occur, whereas the `limit` arguments specifies the maximum length of the array.

If `separator` argument is omitted or not found in the specified string, the entire string is assigned to the first element of the array.

#### Example

```javascript
var fruitsStr = "Apple, Banana, Mango, Orange, Papaya";
var fruitsArr = fruitsStr.split(", ");
document.write(fruitsArr[0]); // Prints: Apple
document.write(fruitsArr[2]); // Prints: Mango
document.write(fruitsArr[fruitsArr.length - 1]); // Prints: Papaya

// Loop through all the elements of the fruits array 
for(var i in fruitsArr) {  
    document.write("<p>" + fruitsArr[i] + "</p>");
}
```

To split a string into an array of characters, specify an empty string (`""`) as a separator.

#### Example

```javascript
var str = "INTERSTELLAR";
var strArr = str.split("");
document.write(strArr[0]); // Prints: I
document.write(strArr[1]); // Prints: N
document.write(strArr[strArr.length - 1]); // Prints: R

// Loop through all the elements of the characters array and print them
for(var i in strArr) {  
    document.write("<br>" + strArr[i]);
}
```

* * *

# Numbers

## Number Type

The _number_ data type is used to represent positive or negative numbers with or without decimal place, or numbers written using exponential notation e.g. 1.5e-4 (equivalent to 1.5x10-4).

#### Example

```javascript
var a = 25;         // integer
var b = 80.5;       // floating-point number
var c = 4.25e+6;    // exponential notation, same as 4.25e6 or 4250000
var d = 4.25e-6;    // exponential notation, same as 0.00000425
```

The Number data type also includes some special values which are: `Infinity`, `-Infinity` and `NaN`. Infinity represents the mathematical Infinity `∞`, which is greater than any number. Infinity is the result of dividing a nonzero number by 0.

#### Example

```javascript
alert(16 / 0);  // Output: Infinity
alert(-16 / 0); // Output: -Infinity
alert(16 / -0); // Output: -Infinity
```

While `NaN` represents a special _Not-a-Number_ value. It is a result of an invalid or an undefined mathematical operation, like taking the square root of -1 or dividing 0 by 0, etc.

#### Example

```javascript
alert("Some text" / 2);       // Output: NaN
alert("Some text" / 2 + 10);  // Output: NaN
alert(Math.sqrt(-1));         // Output: NaN
```

* * *

## Working with Numbers

JavaScript supports both integer and floating-point numbers that can be represented in decimal, hexadecimal or octal notation. Unlike other languages, JavaScript does not treat integer and floating-point numbers differently. All numbers in JavaScript are represented as floating-point numbers. Here's an example demonstrating the numbers in different formats:

#### Example

```javascript
var x = 2;  // integer number
var y = 3.14;  // floating-point number
var z = 0xff;  // hexadecimal number
```

Extra large numbers can be represented in exponential notation e.g. 6.02e+23 (same as 6.02x1023).

#### Example

```javascript
var x = 1.57e4;  // same as 15700
var y = 4.25e+6;  // same as 4.25e6 or 4250000
var z = 4.25e-6;  // same as 0.00000425
```

**Tip:** The biggest safe integer in JavaScript is `9007199254740991 (253-1)`, whereas the smallest safe integer is `-9007199254740991 (-(253-1))`.

Numbers can also be represented in hexadecimal notation (base 16). Hexadecimal numbers are prefixed with `0x`. They are commonly used to represent [colors](https://www.tutorialrepublic.com/css-reference/css-color-values.php). Here's an example:

#### Example

```javascript
var x = 0xff;  // same as 255
var y = 0xb4;  // same as 180
var z = 0x00;  // same as 0
```

**Note:** Integers can be represented in decimal, hexadecimal, and octal notation. Floating-point numbers can be represented in decimal or exponential notation.

* * *

## Operating on Numbers and Strings

As you know from the previous chapters, the `+` operator is used for both addition and concatenation. So, performing mathematical operations on numbers and strings may produce interesting results. The following example will show you what happens when you add numbers and strings:

#### Example

```javascript
var x = 10;
var y = 20;
var z = "30";

// Adding a number with a number, the result will be sum of numbers
console.log(x + y); // 30

// Adding a string with a string, the result will be string concatenation
console.log(z + z); // '3030'

// Adding a number with a string, the result will be string concatenation
console.log(x + z); // '1030'

// Adding a string with a number, the result will be string concatenation
console.log(z + x); // '3010'

// Adding strings and numbers, the result will be string concatenation
console.log("The result is: " + x + y); // 'The result is: 1020'

// Adding numbers and strings, calculation performed from left to right
console.log(x + y + z); // 'The result is: 3030'
```

If you observe the above example carefully, you will find that the result of the last operation is not just a simple string concatenation, because operators with the same precedence are evaluated from _left to right_. That's why, since variables x and y both are numbers they are added first then the result is concatenated with the variable z which is a string, hence final result is `30 + "30" = "3030"`.

But, if you perform other mathematical operations like multiplication, division, or subtraction the result will be different. JavaScript will automatically convert _numeric strings_ (i.e. strings containing numeric values) to _numbers_ in all numeric operations, as shown in the following example:

#### Example

```javascript
var x = 10;
var y = 20;
var z = "30";

// Subtracting a number from a number
console.log(y - x); // 10

// Subtracting a number from a numeric string
console.log(z - x); // 20

// Multiplying a number with a numeric string
console.log(x * z); // 300

// Dividing a number with a numeric string
console.log(z / x); // 3
```

Moreover, if you try to multiply or divide numbers with strings that are not numeric, it returns `NaN` (Not a Number). Also, if you use `NaN` in a mathematical operation, the result will also be `NaN`.

#### Example

```javascript
var x = 10;
var y = "foo";
var z = NaN;

// Subtracting a number from a non-numeric string
console.log(y - x); // NaN

// Multiplying a number with a non-numeric string
console.log(x * y); // NaN

// Dividing a number with a non-numeric string
console.log(x / y); // NaN

// Adding NaN to a number 
console.log(x + z); // NaN

// Adding NaN to a string 
console.log(y + z); // fooNaN
```

* * *

## Representing Infinity

Infinity represents a number too big for JavaScript to handle. JavaScript has special keyword `Infinity` and `-Infinity` to represent positive and negative infinity respectively. For example, dividing by `0` returns `Infinity`, as demonstrated below:

#### Example

```javascript
var x = 5 / 0;
console.log(x); // Infinity

var y = -5 / 0;
console.log(y); // -Infinity
```

**Note:** Infinity is a special value that represents the mathematical Infinity `∞`, which is greater than any number. The [`typeof`](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php#typeof) operator return number for an Infinity value.

* * *

## Avoiding Precision Problems

Sometimes, operations on floating-point numbers produce unexpected results, as shown here:

#### Example

```javascript
var x = 0.1 + 0.2;
console.log(x) // 0.30000000000000004
```

As you can see the result is `0.30000000000000004` rather than the expected `0.3`. This difference is called _representation error_ or _roundoff error_. It occurs because JavaScript and many other languages uses binary (base 2) form to represent decimal (base 10) numbers internally. Unfortunately, most decimal fractions can't be represented exactly in binary form, so small differences occur.

To avoid this problem you can use the solution something like this:

#### Example

```javascript
var x = (0.1 * 10 + 0.2 * 10) / 10;
console.log(x) // 0.3
```

JavaScript round floating-point numbers to 17 digits, which is enough precision or accuracy in most cases. Also, in JavaScript integers (numbers without fractional parts or exponential notation) are accurate is up to 15 digits, as demonstrated in the following example:

#### Example

```javascript
var x = 999999999999999;
console.log(x); // 999999999999999

var y = 9999999999999999;
console.log(y); // 10000000000000000
```

* * *

## Performing Operations on Numbers

JavaScript provides several properties and methods to perform operations on number values. As you already know from the previous chapters, in JavaScript primitive data types can act like objects when you refer to them with the property access notation (i.e. dot notation).

In the following sections, we will look at the number methods that are most commonly used.

## Parsing Integers from Strings

The `parseInt()` method can be used to parse an integer from a string. This method is particularly handy in situations when you are dealing with the values like CSS units e.g. `50px`, `12pt`, etc. and you would like to extract the numeric value out of it.

If the `parseInt()` method encounters a character that is not numeric in the specified base, it stops parsing and returns the integer value parsed up to that point. If the first character cannot be converted into a number, the method will return `NaN` (not a number).

Leading and trailing spaces are allowed. Here's an example:

#### Example

```javascript
console.log(parseInt("3.14"));  // 3
console.log(parseInt("50px"));  // 50
console.log(parseInt("12pt"));  // 12
console.log(parseInt("0xFF", 16));  // 255
console.log(parseInt("20 years"));  // 20
console.log(parseInt("Year 2048"));  // NaN
console.log(parseInt("10 12 2018"));  // 10
```

**Note:** The `parseInt()` method truncates numbers to integer values, but it should not be used as a substitute for `[Math.floor()](https://www.tutorialrepublic.com/javascript-tutorial/javascript-math-operations.php#floor)` method.

Similarly, you can use the `parseFloat()` method to parse floating-point number from a string. The `parseFloat()` method works the same way as the `parseInt()` method, except that it retrieves both integers and numbers with decimals.

#### Example

```javascript
console.log(parseFloat("3.14"));  // 3.14
console.log(parseFloat("50px"));  // 50
console.log(parseFloat("1.6em"));  // 1.6
console.log(parseFloat("124.5 lbs"));  // 124.5
console.log(parseFloat("weight 124.5 lbs"));  // NaN
console.log(parseFloat("6.5 acres"));  // 6.5
```

* * *

## Converting Numbers to Strings

The `toString()` method can be used to convert a number to its string equivalent. This method optionally accepts an integer parameter in the range 2 through 36 specifying the base to use for representing numeric values. Here's an example:

#### Example

```javascript
var x = 10;
var y = x.toString();
console.log(y);  // '10'
console.log(typeof y);  // string
console.log(typeof x);  // number

console.log((12).toString());  // '12'
console.log((15.6).toString());  // '15.6'
console.log((6).toString(2));  // '110'
console.log((255).toString(16));  // 'ff'
```

* * *

## Formatting Numbers in Exponential Notation

You can use the `toExponential()` method to format or represent a number in exponential notation. This method optionally accepts an integer parameter specifying the number of digits after the decimal point. Also, the returned value is a string not a number. Here's an example:

#### Example

```javascript
var x = 67.1234;

console.log(x.toExponential());  // 6.71234e+1
console.log(x.toExponential(6));  // 6.712340e+1
console.log(x.toExponential(4));  // 6.7123e+1
console.log(x.toExponential(2));  // 6.71e+1
```

**Note:** Exponential notation is useful for representing numbers that are either very large or very small in magnitude. For example, 62500000000 can be written as 625e+8 or 6.25e+10.

* * *

## Formatting Numbers to Fixed Decimals

You can use the `toFixed()` method when you want to format a number with a fixed number of digits to the right of the decimal point. The value returned by this method is a string and it has exactly specified number of `digits` after the decimal point. If the `digits` parameter is not specified or omitted, it is treated as 0. Here's an example:

#### Example

```javascript
var x = 72.635;

console.log(x.toFixed());  // '73' (note rounding, no fractional part)
console.log(x.toPrecision(2));  // '72.64' (note rounding)
console.log(x.toPrecision(1));  // '72.6'

var y = 6.25e+5;
console.log(y.toFixed(2)); // '625000.00'

var z = 1.58e-4;
console.log(z.toFixed(2));  // '0.00' (since 1.58e-4 is equal to 0.000158)
```

* * *

## Formatting Numbers with Precision

If you want most appropriate form of a number, you can use the `toPrecision()` method instead. This method returns a string representing the number to the specified precision.

If precision is large enough to include all the digits of the integer part of number, then the number is formatted using fixed-point notation. Otherwise, the number is formatted using exponential notation. The precision parameter is optional. Here's an example:

#### Example

```javascript
var x = 6.235;

console.log(x.toPrecision());  // '6.235'
console.log(x.toPrecision(3));  // '6.24' (note rounding)
console.log(x.toPrecision(2));  // '6.2'
console.log(x.toPrecision(1));  // '6'

var y = 47.63;
console.log(y.toPrecision(2)); // '48' (note rounding, no fractional part)

var z = 1234.5;
console.log(z.toPrecision(2));  // '1.2e+3'
```

* * *

## Finding the Largest and Smallest Possible Numbers

The Number object also has several properties associated with it. The `Number.MAX_VALUE` and `Number.MIN_VALUE` properties of the Number object represent the largest and smallest (closest to zero, not most negative) possible positive numbers that JavaScript can handle. They are constants and their actual values are `1.7976931348623157e+308`, and `5e-324`, respectively.

A number that falls outside of the range of possible numbers is represented by a constant `Number.POSITIVE_INFINITY` or `Number.NEGATIVE_INFINITY`. Here's an example:

#### Example

```javascript
var a = Number.MAX_VALUE;
console.log(a); // 1.7976931348623157e+308

var b = Number.MIN_VALUE;
console.log(b); // 5e-324

var x = Number.MAX_VALUE * 2;
console.log(x); // Infinity

var y = -1 * Number.MAX_VALUE * 2;
console.log(y); // -Infinity
```

* * *

## Boolean Type

The Boolean data type can hold only two values: `true` or `false`. It is typically used to store values like yes (`true`) or no (`false`), on (`true`) or off (`false`), etc. as demonstrated below:

#### Example

```javascript
var isReading = true;   // yes, I'm reading
var isSleeping = false; // no, I'm not sleeping
```

Boolean values also come as a result of comparisons in a program. The following example compares two variables and shows the result in an alert dialog box:

#### Example

```javascript
var a = 2, b = 5, c = 10;

alert(b > a) // Output: true
alert(b > c) // Output: false
```

You will learn more about the comparisons in [JavaScript if/else](https://www.tutorialrepublic.com/javascript-tutorial/javascript-if-else-statements.php) chapter.

* * *

## Undefined Type

The undefined data type can only have one value-the special value `undefined`. If a variable has been declared, but has not been assigned a value, has the value `undefined`.

#### Example

```javascript
var a;
var b = "Hello World!"

alert(a) // Output: undefined
alert(b) // Output: Hello World!
```

* * *

## Null Type

This is another special data type that can have only one value-the `null` value. A `null` value means that there is no value. It is not equivalent to an empty string (`""`) or 0, it is simply nothing.

A variable can be explicitly emptied of its current contents by assigning it the `null` value.

#### Example

```javascript
var a = null;
alert(a); // Output: null

var b = "Hello World!"
alert(b); // Output: Hello World!

b = null;
alert(b) // Output: null
```

* * *

## The Object Data Type

The `object` is a complex data type that allows you to store collections of data.

An object contains properties, defined as a key-value pair. A property key (name) is always a string, but the value can be any data type, like strings, numbers, booleans, or complex data types like arrays, function and other objects. You'll learn more about objects in upcoming chapters.

The following example will show you the simplest way to create an object in JavaScript.

#### Example

```javascript
var emptyObject = {};
var person = {"name": "Clark", "surname": "Kent", "age": "36"};

// For better reading
var car = {
    "modal": "BMW X3",
    "color": "white",
    "doors": 5
}
```

You can omit the quotes around property name if the name is a valid JavaScript name. That means quotes are required around `"first-name"` but are optional around `firstname`. So the car object in the above example can also be written as:

#### Example

```javascript
var car = {
    modal: "BMW X3",
    color: "white",
    doors: 5
}
```

Ref : [Objects](:/12f9730ea1154c4fab8afe5dcc2d94e2)

* * *

## The Array Type

An array is a type of object used for storing multiple values in single variable. Each value (also called an element) in an array has a numeric position, known as its index, and it may contain data of any data type-numbers, strings, booleans, functions, objects, and even other arrays. The array index starts from 0, so that the first array element is `arr[0]` not `arr[1]`.

The simplest way to create an array is by specifying the array elements as a comma-separated list enclosed by square brackets.

#### Example

```javascript
var colors = ["Red", "Yellow", "Green", "Orange"];
var cities = ["London", "Paris", "New York"];

alert(colors[0]);   // Output: Red
alert(cities[2]);   // Output: New York
```

Ref : [Arrays](:/19438d8a4a964c0ea3f9e5a662c2e646)

* * *

## The Function Type

The function is callable object that executes a block of code. Since functions are objects, so it is possible to assign them to variables.

#### Example

```javascript
var greeting = function(){ 
    return "Hello World!"; 
}

// Check the type of greeting variable
alert(typeof greeting) // Output: function
alert(greeting());     // Output: Hello World!
```

In fact, functions can be used at any place any other value can be used. Functions can be stored in variables, objects, and arrays. Functions can be passed as arguments to other functions, and functions can be returned from functions.

#### Example

```javascript
function createGreeting(name){
    return "Hello, " + name;
}
function displayGreeting(greetingFunction, userName){
    return greetingFunction(userName);
}

var result = displayGreeting(createGreeting, "Peter");
alert(result); // Output: Hello, Peter
```

Ref : [Functions](:/997162c9e1284e509674f4b756a17085)

* * *

## The typeof Operator

The `typeof` operator can be used to find out what type of data a variable or operand contains. It can be used with or without parentheses (`typeof(x)` or `typeof x`).

The `typeof` operator is particularly useful in the situations when you need to process the values of different types differently, but you need to be very careful, because it may produce unexpected result in some cases, as demonstrated in the following example:

#### Example

```javascript
// Numbers
typeof 15;  // Returns: "number"
typeof 42.7;  // Returns: "number"
typeof 2.5e-4;  // Returns: "number"
typeof Infinity;  // Returns: "number"
typeof NaN;  // Returns: "number". Despite being "Not-A-Number"

// Strings
typeof '';  // Returns: "string"
typeof 'hello';  // Returns: "string"
typeof '12';  // Returns: "string". Number within quotes is typeof string

// Booleans
typeof true;  // Returns: "boolean"
typeof false;  // Returns: "boolean"

// Undefined
typeof undefined;  // Returns: "undefined"
typeof undeclaredVariable; // Returns: "undefined"

// Null
typeof Null;  // Returns: "object"

// Objects
typeof {name: "John", age: 18};  // Returns: "object"

// Arrays
typeof [1, 2, 4];  // Returns: "object"

// Functions
typeof function(){};  // Returns: "function"
```

As you can clearly see in the above example when we test the `null` value using the `typeof` operator (_line no-22_), it returned "object" instead of "null".

This is a long-standing bug in JavaScript, but since lots of codes on the web written around this behavior, and thus fixing it would create a lot more problem, so idea of fixing this issue was rejected by the committee that design and maintains JavaScript.

* * *