Type Conversions

# Type Conversions

## Automatic Type Conversions

Most of the time JavaScript automatically converts values from one data type to another when used in expression. For example, in mathematical operations values are automatically converted to numbers. However, the end result is not always what you expected:

#### Example

```js
alert("3" - 2);  // Outputs: 1 
alert("3" + 2);  // Outputs: "32" (because + is also concatenation operator)
alert(3 + "2");  // Outputs: "32"
alert("3" * "2");  // Outputs: 6
alert("10" / "2");  // Outputs: 5
alert(1 + true);  // Outputs: 2 (because true is converted to 1)
alert(1 + false);  // Outputs: 1 (because false is converted to 0)
alert(1 + undefined);  // Outputs: NaN
alert(3 + null);  // Outputs: 3 (because null is converted to 0)
alert("3" + null);  // Outputs: "3null"
alert(true + null);  // Outputs: 1
alert(true + undefined);  // Outputs: NaN
```

There are situations when we need to manually convert a value from one data type to another. JavaScript provides a number of different methods to perform such data type conversion task. In the following sections we will discuss those methods in detail.

## Converting Values to Numbers

The numeric conversion is usually required when we read the value from a string-based source like a text input, but we expect a number to be entered, or want to treat it as a number.

In such situations, you can use the global method `Number()` to convert strings to numbers.

#### Example

```js
var str = "123";
alert(typeof str); // Outputs: string

var num = Number(str); // Becomes a number 123
alert(typeof num); // Outputs: number
```

If the string is not a valid number, the result will be `NaN`. Empty strings convert to 0.

#### Example

```js
Number("10.5")  // returns 10.5
Number(true)  // returns 1
Number(false)  // returns 0
Number(null)  // returns 0
Number(" 123 ")  // returns 123
Number(" ")  // returns 0
Number("")  // returns 0
Number("123e-1")  // returns 12.3
Number("0xFF") // returns 255 (hexadecimal representation)
Number("undefined")  // returns NaN
Number("null")  // returns NaN
Number("Hello World!")  // returns NaN
```

* * *

## Converting Values to Strings

Similarly, you can use the `String()` method to convert a value to a string.

The following example will show you how to convert a Boolean value to a string.

#### Example

```js
var bool = true;
alert(typeof bool); // Outputs: boolean

var str = String(bool); // Becomes a string "true"
alert(typeof str); // Outputs: string
```

The `String()` method can be used on any type of numbers, variables, or expressions:

#### Example

```js
String(10.5)  // returns "10.5"
String(123)  // returns "123"
String(100 + 23)  // returns "123"
String(true)  // returns "true"
String(false)  // returns "false"
String(123e-1)  // returns "12.3"
String(0xFF) // returns "255"
String(undefined)  // returns "undefined"
String(null)  // returns "null"
```

Another technique for converting numbers to strings is using the `toString()` method:

#### Example

```js
var num = 123;
alert(typeof num); // Outputs: number

var str = num.toString(); // Becomes a string "123"
alert(typeof str); // Outputs: string
```

* * *

## Converting Values to Boolean

Boolean conversions are also pretty straight forward. You can use the `Boolean()` method to convert any value to a Boolean value (i.e. `true` or `false`).

Values that are intuitively empty, like `0`, `null`, `false`, `undefined`, `NaN` or an empty string (`""`) become `false`. Other values become `true`, as shown in the example here:

#### Example

```js
Boolean(0) // returns false
Boolean(null)  // returns false
Boolean(false)  // returns false
Boolean(undefined)  // returns false
Boolean(NaN)  // returns false
Boolean("") // returns false
Boolean("0") // returns true
Boolean(1) // returns true
Boolean(true) // returns true
Boolean("false") // returns true
Boolean("Hello World!") // returns true
Boolean(" ") // returns true
```

If you see the example carefully you'll find the `Boolean()` method returns `true` for the string with zero "0", and string "false", whereas it returns `false` for the values 0 and false.

**Note:** In some programming languages (namely PHP) the string "0" is treated as `false`. But in JavaScript a non-empty string is always `true`.

* * *

## Object to Primitive Conversions

All the conversions we've seen so far are performed on primitive types (data types that can hold only a single value at a time). But what happens with complex data types such as object, let's see.

JavaScript automatically perform object-to-string conversion when we try to print out an object like `alert(obj)` or `document.write(obj)`. Likewise, the object-to-number conversions are automatically performed when we try to add or subtract objects or apply mathematical functions, for example, adding or subtracting date objects. Here's an example:

#### Example

```js
var date1 = new Date(2018, 5, 24);
alert(date1); // Display date string like: Sun Jun 24 2018 00:00:00

var date2 = new Date(2025, 8, 15);
var time = date2 - date1;
alert(time) // Display time in milliseconds: 228096000000
```

You can also perform the object-to-string conversion manually using the `toString()` method, which return a string representation of the object. Additionally, you can use the `valueOf()` method on some objects such as Date to perform object-to-number conversion. Here's an example:

#### Example

```js
var arr = [1, 2, 3];
arr.toString(); // returns "1,2,3"

var d = new Date(2018, 5, 24);
d.toDateString(); // returns date like Sun Jun 24 2018 00:00:00
d.valueOf(); // returns 1529778600000
```

**Note:** Object-to-Boolean conversion are insignificant, because all objects (including arrays and functions) are true in a boolean context. So there are only string and numeric conversions.

* * *

## Type Conversions Using Operators

Certain JavaScript operators, such as `+` and `-` operators, can also be used to perform type conversions, as demonstrated in the following example:

#### Example

```js
var x = "10"; // x is a string
var y = +x;
alert(typeof(y)); // Outputs: number
alert(y); // Outputs: 10

var x = 10; // x is a number
var y = x + "";
alert(typeof(y)); // Outputs: string
alert(y); // Outputs: 10

var x = "15"; // x is a string
var y = x - 0;
alert(typeof(y)); // Outputs: number
alert(y); // Outputs: 15

var x = "123";
alert(typeof(!!x)); // Outputs: boolean
alert(!!x); // Outputs: true

var x = "Hello World!";
var y = +x;
alert(typeof(y));// Outputs: number
alert(y); // Outputs: NaN
```

We hope you've understood the basics of data type conversions. Please, check out the chapter on [JavaScript data types](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php) to learn more about the different data types available in JavaScript.

* * *