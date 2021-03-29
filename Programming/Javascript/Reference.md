Reference


# **Boolean :**

* properties and method of the global Boolean object.*

## The JavaScript Boolean Object

The Boolean object is an object wrapper around the boolean value `true` or `false`. This Boolean object type exists primarily to provide a `toString()` method to convert boolean values to strings.

## Boolean Properties

*standard properties of the Boolean object.*

| Property | Description |
| --- | --- |
| `prototype` | Allows you to add new properties and methods to a Boolean object. |

**Note:** Every object in JavaScript has a `constructor` property that refers to the constructor function that was used to create the instance of that object.

* * *

## Boolean Methods

The following table lists the standard methods of the Boolean object.

| Method | Description |
| --- | --- |
| `toString()` | Converts a Boolean value to a string, and returns the result. |
| `valueOf()` | Returns the primitive value of a Boolean object. |

* * *
* * *

# **Number :**

*Properties and method of the global Number object.*

## The JavaScript Number Object

The JavaScript Number object acts as a wrapper for primitive numeric values. JavaScript has only one kind of number data type and it doesn't distinguish between integers and floating-point values.


## Number Properties

*Standard properties of the Number object.*

| Property | Description |
| --- | --- |
| `MIN_SAFE_INTEGER` | Represents the maximum safe integer in JavaScript (253 - 1). |
| `MAX_VALUE` | Returns the largest numeric value representable in JavaScript, approximately 1.79E+308. Values larger than `MAX_VALUE` are represented as `Infinity`. |
| `MIN_SAFE_INTEGER` | Represents the minimum safe integer in JavaScript (-(253 - 1)). |
| `MIN_VALUE` | Returns the smallest positive numeric value representable in JavaScript, approximately 5e-324. It is closest to 0, not the most negative number. Values smaller than `MIN_VALUE` are converted to 0. |
| `NEGATIVE_INFINITY` | Represents the negative infinity value. |
| `NaN` | Represents "Not-A-Number" value. |
| `POSITIVE_INFINITY` | Represents the infinity value. |
| `prototype` | Allows you to add new properties and methods to a Number object. |

**Note:** Every object in JavaScript has a `constructor` property that refers to the constructor function that was used to create the instance of that object.

* * *

## Number Methods

*Standard methods of the Number object*.

| Method | Description |
| --- | --- |
| `isFinite()` | Checks whether the passed value is a finite number. |
| `isInteger()` | Checks whether the passed value is an integer. |
| `isNaN()` | Checks whether the passed value is `NaN` and its type is Number. |
| `isSafeInteger()` | Checks whether a value is a safe integer. |
| `toExponential()` | Converts a number to exponential notation. |
| `toFixed()` | Formats a number using fixed-point notation. |
| `toPrecision()` | Returns a string representing the number to the specified precision. |
| `toString()` | Converts a number to a string. |
| `valueOf()` | Returns the primitive value of a Number object. |

* * *
* * *


# **String :**
*Properties and method of the global String object.*

## The JavaScript String Object

The JavaScript String object is a global object that is used to store strings. A string is a sequence of letters, numbers, special characters and arithmetic values or combination of all.

## String Properties

*Standard properties of the String object.*

| Property | Description |
| --- | --- |
| `length` | Returns the length of a string. |
| `prototype` | Allows you to add new properties and methods to an String object. |

**Note:** Every object in JavaScript has a `constructor` property that refers to the constructor function that was used to create the instance of that object.

* * *

## String Methods

*Standard methods of the String object.*

| Method | Description |
| --- | --- |
| `charAt()` | Returns the character at the specified index. |
| `charCodeAt()` | Returns the Unicode of the character at the specified index. |
| `concat()` | Joins two or more strings, and returns a new string. |
| `endsWith()` | Checks whether a string ends with a specified substring. |
| `fromCharCode()` | Converts Unicode values to characters. |
| `includes()` | Checks whether a string contains the specified substring. |
| `indexOf()` | Returns the index of the first occurrence of the specified value in a string. |
| `lastIndexOf()` | Returns the index of the last occurrence of the specified value in a string. |
| `localeCompare()` | Compares two strings in the current locale. |
| `match()` | Matches a string against a regular expression, and returns an array of all matches. |
| `repeat()` | Returns a new string which contains the specified number of copies of the original string. |
| `replace()` | Replaces the occurrences of a string or pattern inside a string with another string, and return a new string without modifying the original string. |
| `search()` | Searches a string against a regular expression, and returns the index of the first match. |
| `slice()` | Extracts a portion of a string and returns it as a new string. |
| `split()` | Splits a string into an array of substrings. |
| `startsWith()` | Checks whether a string begins with a specified substring. |
| `substr()` | Extracts the part of a string between the start index and a number of characters after it. |
| `substring()` | Extracts the part of a string between the start and end indexes. |
| `toLocaleLowerCase()` | Converts a string to lowercase letters, according to host machine's current locale. |
| `toLocaleUpperCase()` | Converts a string to uppercase letters, according to host machine's current locale. |
| `toLowerCase()` | Converts a string to lowercase letters. |
| `toString()` | Returns a string representing the specified object. |
| `toUpperCase()` | Converts a string to uppercase letters. |
| `trim()` | Removes whitespace from both ends of a string. |
| `valueOf()` | Returns the primitive value of a String object. |

* * *
* * *

# **Array :**

*overview of the properties and method of the global array object.*

## The JavaScript Array Object

The JavaScript Array object is a global object that is used in the construction of arrays. An array is a special type of variable that allows you to store multiple values in a single variable.

## Array Properties

*standard properties of the Array object.*

| Property | Description |
| --- | --- |
| `length` | Sets or returns the number of elements in an array. |
| `prototype` | Allows you to add new properties and methods to an Array object. |

**Note:** Every object in JavaScript has a `constructor` property that refers to the constructor function that was used to create the instance of that object.

* * *

## Array Methods

The following table lists the standard methods of the Array object.

| Method | Description |
| --- | --- |
| `concat()` | Merge two or more arrays, and returns a new array. |
| `copyWithin()` | Copies part of an array to another location in the same array and returns it. |
| `entries()` | Returns a key/value pair Array Iteration Object. |
| `every()` | Checks if every element in an array pass a test in a testing function. |
| `fill()` | Fill the elements in an array with a static value. |
| `filter()` | Creates a new array with all elements that pass the test in a testing function. |
| `find()` | Returns the value of the first element in an array that pass the test in a testing function. |
| `findIndex()` | Returns the index of the first element in an array that pass the test in a testing function. |
| `forEach()` | Calls a function once for each array element. |
| `from()` | Creates an array from an object. |
| `includes()` | Determines whether an array includes a certain element. |
| `indexOf()` | Search the array for an element and returns its first index. |
| `isArray()` | Determines whether the passed value is an array. |
| `join()` | Joins all elements of an array into a string. |
| `keys()` | Returns a Array Iteration Object, containing the keys of the original array. |
| `lastIndexOf()` | Search the array for an element, starting at the end, and returns its last index. |
| `map()` | Creates a new array with the results of calling a function for each array element. |
| `pop()` | Removes the last element from an array, and returns that element. |
| `push()` | Adds one or more elements to the end of an array, and returns the array's new length. |
| `reduce()` | Reduce the values of an array to a single value (from left-to-right). |
| `reduceRight()` | Reduce the values of an array to a single value (from right-to-left). |
| `reverse()` | Reverses the order of the elements in an array. |
| `shift()` | Removes the first element from an array, and returns that element. |
| `slice()` | Selects a part of an array, and returns the new array. |
| `some()` | Checks if any of the elements in an array passes the test in a testing function. |
| `sort()` | Sorts the elements of an array. |
| `splice()` | Adds/Removes elements from an array. |
| `toString()` | Converts an array to a string, and returns the result. |
| `unshift()` | Adds new elements to the beginning of an array, and returns the array's new length. |
| `values()` | Returns a Array Iteration Object, containing the values of the original array. |

* * *
* * *

# **Date :**

*Properties and method of the global Date object.*

## The JavaScript Date Object

The JavaScript Date object is a global object that is used to work with dates and times. The Date objects are based on a time value that is the number of milliseconds since January 1, 1970 UTC.


## Date Properties

*standard properties of the Date object.*

| Property | Description |
| --- | --- |
| `prototype` | Allows you to add new properties and methods to a Date object. |

**Note:** Every object in JavaScript has a `constructor` property that refers to the constructor function that was used to create the instance of that object.

* * *

## Date Methods

The following table lists the standard methods of the Date object.

| Method | Description |
| --- | --- |
| `getDate()` | Returns the day of the month (from 1-31). |
| `getDay()` | Returns the day of the week (from 0-6). |
| `getFullYear()` | Returns the year (four digits). |
| `getHours()` | Returns the hour (from 0-23). |
| `getMilliseconds()` | Returns the milliseconds (from 0-999). |
| `getMinutes()` | Returns the minutes (from 0-59). |
| `getMonth()` | Returns the month (from 0-11). |
| `getSeconds()` | Returns the seconds (from 0-59). |
| `getTime()` | Returns the number of milliseconds since midnight Jan 1, 1970. |
| `getTimezoneOffset()` | Returns the time difference between UTC time and local time, in minutes. |
| `getUTCDate()` | Returns the day of the month, according to universal time (from 1-31). |
| `getUTCDay()` | Returns the day of the week, according to universal time (from 0-6). |
| `getUTCFullYear()` | Returns the year, according to universal time. |
| `getUTCHours()` | Returns the hour, according to universal time (from 0-23). |
| `getUTCMilliseconds()` | Returns the milliseconds, according to universal time (from 0-999) |
| `getUTCMinutes()` | Returns the minutes, according to universal time (from 0-59). |
| `getUTCMonth()` | Returns the month, according to universal time (from 0-11). |
| `getUTCSeconds()` | Returns the seconds, according to universal time (from 0-59). |
| getYear() | Deprecated. Use the `getFullYear()` method instead. |
| `now()` | Returns the number of milliseconds since midnight Jan 1, 1970. |
| `parse()` | Parses a date string and returns the number of milliseconds since Jan 1, 1970. |
| `setDate()` | Sets the day of the month of a date object. |
| `setFullYear()` | Sets the full year of a date object. |
| `setHours()` | Sets the hours of a date object. |
| `setMilliseconds()` | Sets the milliseconds of a date object. |
| `setMinutes()` | Set the minutes of a date object. |
| `setMonth()` | Sets the month of a date object. |
| `setSeconds()` | Sets the seconds of a date object. |
| `setTime()` | Sets a date to a specified number of milliseconds after/before Jan 1, 1970. |
| `setUTCDate()` | Sets the day of the month of a date object, according to universal time. |
| `setUTCFullYear()` | Sets the year of a date object, according to universal time. |
| `setUTCHours()` | Sets the hours of a date object, according to universal time. |
| `setUTCMilliseconds()` | Sets the milliseconds of a date object, according to universal time. |
| `setUTCMinutes()` | Set the minutes of a date object, according to universal time. |
| `setUTCMonth()` | Sets the month of a date object, according to universal time. |
| `setUTCSeconds()` | Set the seconds of a date object, according to universal time. |
| `setYear()` | Deprecated. Use the `setFullYear()` method instead. |
| `toDateString()` | Converts the date portion of a Date object into a human readable form. |
| `toGMTString()` | Deprecated. Use the toUTCString() method instead |
| `toISOString()` | Returns the date as a string, formatted according to ISO standard. |
| `toJSON()` | Returns the date as a string, formatted as a JSON date. |
| `toLocaleDateString()` | Returns the date portion of a Date object as a locally formatted string. |
| `toLocaleTimeString()` | Returns the time portion of a Date object as a locally formatted string. |
| `toLocaleString()` | Converts a Date object to a locally formatted string. |
| `toString()` | Converts a Date object to a string. |
| `toTimeString()` | Converts the time portion of a Date object to a string. |
| `toUTCString()` | Converts a Date object to a string, according to universal time. |
| `UTC()` | Returns the number of milliseconds in a Date object since January 1, 1970, 00:00:00 (midnight), universal time. |
| `valueOf()` | Returns the primitive value of a Date object. |

* * *
* * *


# **Math :**

This chapter contains a brief overview of the properties and method of the global Math object.

## The JavaScript Math Object

The JavaScript Math object is used to perform mathematical tasks. The Math object is a static built-in object, so you won't need to instantiate it, all its properties and methods can be accessed directly.

## Math Properties

Standard properties of the Math object.

| Property | Description |
| --- | --- |
| `E` | Returns Euler's number, the base of natural logarithms, `e`, approximately 2.718 |
| `LN2` | Returns the natural logarithm of 2, approximately 0.693 |
| `LN10` | Returns the natural logarithm of 10, approximately 2.302 |
| `LOG2E` | Returns the base 2 logarithm of `e`, approximately 1.442 |
| `LOG10E` | Returns the base 10 logarithm of `e`, approximately 0.434 |
| `PI` | Returns the ratio of the circumference of a circle to its diameter (i.e. `π`). The approximate value of PI is 3.14159 |
| `SQRT1_2` | Returns the square root of 1/2, approximately 0.707 |
| `SQRT2` | Returns the square root of 2, approximately 1.414 |

**Note:** The Math object is just a collection of static functions and constants. The Math object is different from other built-in objects (e.g. Date, Array, String, etc.), because it has no constructor, so there is no way to create an instance of Math.

* * *

## Math Methods

*Standard methods of the Math object.*

| Method | Description |
| --- | --- |
| `abs()` | Returns the absolute value of a number. |
| `acos()` | Returns the arccosine of a number, in radians. |
| `acosh()` | Returns the hyperbolic arccosine of a number. |
| `asin()` | Returns the arcsine of a number, in radians |
| `asinh()` | Returns the hyperbolic arcsine of a number. |
| `atan()` | Returns the arctangent of a number, in radians. |
| `atan2(y, x)` | Returns the arctangent of the quotient of its arguments. |
| `atanh()` | Returns the hyperbolic arctangent of a number. |
| `cbrt()` | Returns the cube root of a number. |
| `ceil()` | Returns the next integer greater than or equal to a given number (rounding up). |
| `cos()` | Returns the cosine of the specified angle. The angle must be specified in radians. |
| `cosh()` | Returns the hyperbolic cosine of a number. |
| `exp(x)` | Returns `ex`, where `x` is the argument, and `e` is Euler's number (also known as Napier's constant), the base of the natural logarithms. |
| `floor()` | Returns the next integer less than or equal to a given number (rounding down). |
| `log()` | Returns the natural logarithm (base `e`) of a number. |
| `max(x, y, ...)` | Returns the highest-valued number in a list of numbers. |
| `min(x, y, ...)` | Returns the lowest-valued number in a list of numbers. |
| `pow(x, y)` | Returns the base to the exponent power, that is, `xy`. |
| `random()` | Returns a random number between 0 and 1 (including 0, but not 1). |
| `round()` | Returns the value of a number rounded to the nearest integer. |
| `sin()` | Returns the sign of a number (given in radians). |
| `sinh()` | Returns the hyperbolic sine of a number. |
| `sqrt()` | Returns the square root of a number. |
| `tan()` | Returns the tangent of a number. |
| `tanh()` | Returns the hyperbolic tangent of a number. |
| `trunc(x)` | Returns the integer part of a number by removing any fractional digits. |

* * * 
* * *

# **Reserved Keywords :**

| JavaScript Reserved Words |     |     |
| --- | --- | --- |
| break | export | return |
| case | for | switch |
| comment | function | this |
| continue | if  | typeof |
| default | import | var |
| delete | in  | void |
| do  | label | while |
| else | new | with |
* * *
| Java Keywords (Reserved by JavaScript) |     |     |
| --- | --- | --- |
| abstract | implements | protected |
| boolean | instanceOf | public |
| byte | int | short |
| char | interface | static |
| double | long | synchronized |
| false | native | throws |
| final | null | transient |
| float | package | true |
| goto | private |     |
* * *
| ECMAScipt Reserved Words |     |     |
| --- | --- | --- |
| catch | enum | throw |
| class | extends | try |
| const | finally |     |
| debugger | super |     |
* * *
| Other JavaScript Keywords |     |     |
| --- | --- | --- |
| alert | isFinite | personalbar |
| Anchor | isNan | Plugin |
| Area | java | print |
| arguments | JavaArray | prompt |
| Array | JavaClass | prototype |
| assign | JavaObject | Radio |
| blur | JavaPackage | ref |
| Boolean | length | RegExp |
| Button | Link | releaseEvents |
| callee | location | Reset |
| caller | Location | resizeBy |
| captureEvents | locationbar | resizeTo |
| Checkbox | Math | routeEvent |
| clearInterval | menubar | scroll |
| clearTimeout | MimeType | scrollbars |
| close | moveBy | scrollBy |
| closed | moveTo | scrollTo |
| confirm | name | Select |
| constructor | NaN | self |
| Date | navigate | setInterval |
| defaultStatus | navigator | setTimeout |
| document | Navigator | status |
| Document | netscape | statusbar |
| Element | Number | stop |
| escape | Object | String |
| eval | onBlur | Submit |
| FileUpload | onError | sun |
| find | onFocus | taint |
| focus | onLoad | Text |
| Form | onUnload | Textarea |
| Frame | open | toolbar |
| Frames | opener | top |
| Function | Option | toString |
| getClass | outerHeight | unescape |
| Hidden | OuterWidth | untaint |
| history | Packages | unwatch |
| History | pageXoffset | valueOf |
| home | pageYoffset | watch |
| Image | parent | window |
| Infinity | parseFloat | Window |
| InnerHeight | parseInt |     |
| InnerWidth | Password |     |

* * *
