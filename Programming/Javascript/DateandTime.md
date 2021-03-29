Date and Time

# Date and Time

## Using the Date Object

The Date object is a built-in JavaScript object. It allows you to get the user's local time by accessing the computer system clock through the browser. The Date object also provides several methods for managing, manipulating, and formatting dates and times.

## Creating a Date Object

Before we start working with the date and time, we need to create a Date object. Unlike other built-in objects, such as arrays or functions, dates don't have a corresponding literal form: all date objects need to be created using the Date constructor function which is `Date()`.

There are four different ways to create a Date object in JavaScript.

## The `new Date()` Syntax

You can simply declare a new Date object without initializing its value. In this case, the date and time value will be set to the current date and time on the user's device on which the script is run.

#### Example

```js
var d = new Date();
document.write(d);
```

## The new Date(_year_, _month_, ...) Syntax

You can also initialize a Date object by passing the following parameters separated by commas: year, month, day, hours, minutes, seconds, and milliseconds.

The year and month parameters are required other parameters are optional.

#### Example

```js
var d = new Date(2018,0,31,14,35,20,50);
document.write(d);
```

This date is actually represent 31 January 2018 at 14:35:20 and 50 milliseconds. You can ignore the time part and specify just the date part if you wish.

## The new Date(_dateString_) Syntax

JavaScript also allows you to create a Date object by passing the string representing a date, or a date and time, as shown in the following example:

#### Example

```js
var d = new Date("31 January 2018");
document.write(d);
```

This date represents 31 January 2018. You can also specify strings like Jan 31 2018, or any of a number of valid variations, JavaScript will automatically handle that.

## The new Date(_milliseconds_) Syntax

You can also define a Date object by passing the number of milliseconds since January 1, 1970, at 00:00:00 GMT. This time is known as the _UNIX epoch_ because 1970 was the year when the UNIX operating system was formally introduced. Here's an example:

#### Example

```js
var d = new Date(1517356800000);
document.write(d);
```

The above date represents Wednesday 31 January 2018 05:30:00 GMT+0530.

Once you have created an instance of the Date object, you can use its methods to perform various tasks, such as getting different component of a date, setting or modifying individual date and time value, etc. These methods are described in detail in the following sections.

**Note:** JavaScript provides shortcuts called "literals" for creating most of the native object without having to use the `new` operator, like `new Object()`, `new Array()`, etc.

* * *

## Getting the Current Date and Time

To get the current date and time, create a new Date object without passing any parameters. This will create an object with the current date and time. Here's an example:

#### Example

```js
var now = new Date();
alert(now); // Display the current date and time
```

The output of this example will look something like this (depending on time zone offset):

Wed Dec 25 2019 18:14:32 GMT+0100 (Central European Standard Time)

* * *

## Creating the Date and Time Strings

The JavaScript Date object provides several methods, such as `toDateString()`, `toLocaleDateString()`, etc. to generate date strings in different formats. Here's is an example:

#### Example

```js
var d = new Date();
alert(d.toDateString()); // Display an abbreviated date string
alert(d.toLocaleDateString()); // Display a localized date string
alert(d.toISOString()); // Display the ISO standardized date string
alert(d.toUTCString()); // Display a date string converted to UTC time
alert(d.toString()); // Display the full date string with local time zone
```

Similarly, you can use the `toLocaleTimeString()`, `toTimeString()` methods of the Date object to generate time strings, as shown in the following example:

#### Example

```js
var d = new Date();
alert(d.toTimeString()); // Display the time portion of the date
alert(d.toLocaleTimeString()); // Display a localized time string
```

* * *

## Getting Specific Date and Time Components

Once you have a proper date object, a number of methods are available to you to extract details from it, such as the month, date, hours or minutes value etc. The following section describes the various methods of extracting individual pieces of information from a Date object.

## Getting the Year, Month and Date

The Date object provides several methods such as `getFullYear()`, `getMonth()`, `getDay()`, etc. that you can use to extract the specific date components from the Date object, such as year, day of month, day of week, etc. respectively. The following example demonstrates how to get specific date components from the Date object using these methods:

#### Example

```js
var d = new Date();
// Extracting date part
alert(d.getDate()); // Display the day of the month
alert(d.getDay()); // Display the number of days into the week (0-6)
alert(d.getMonth()); // Display the number of months into the year (0-11)
alert(d.getFullYear()); // Display the full year (four digits)
```

The `getDay()` method returns a number representing the day of the week (from 0 to 6) instead of returning a name such as Sunday or Monday in such a way that, if it is Sunday, the method returns 0; and if it is Monday , the method returns 1, and so on.

Likewise, the `getMonth()` method returns the number of months (from 0 to 11) instead of name of the month. Here 0 represents the first month of the year. Therefore, if it is January the method returns 0 not 1; and if it is August, the method returns 7.

## Getting the Hours, Minutes, Seconds, and Milliseconds

Similarly, the Date object provides methods like `getHours()`, `getMinutes()`, `getSeconds()`, `getTimezoneOffset()` etc. to extract the time components from the Date object.

#### Example

```js
var d = new Date();
// Extracting time part 
alert(d.getHours()); // Display the number of hours into the day (0-23)
alert(d.getMinutes()); // Display the number of minutes into the hour (0-59)
alert(d.getSeconds()); // Display the seconds into the minute (0-59)
alert(d.getMilliseconds()); // Display the number of milliseconds into second (0-999)
alert(d.getTime()); // Display the number of milliseconds since 1/1/1970
alert(d.getTimezoneOffset()); // Display the time-zone offset (from Greenwich Mean Time) in minutes
```

The `getHours()` method returns the number of hours into the day (from 0 to 23) according to the 24-hour clock. So, when it is midnight, the method returns 0; and when it is 3:00 P.M., it returns 15.

**Note:** The Date objects also have methods to obtain the UTC components. Just place UTC after get, such as `getUTCDate()`, `getUTCHour()`, `getUTCMinutes()`, and so on.

* * *

## Setting the Date and Time Values

In addition to retrieving date and time values, you can also set or modify these values using the JavaScript. This is most often used in program where you have to change the value of a date object from one particular date or time to another. Let's see how it works.

## Setting the Year, Month and Date

The Date object provides methods such as `setFullYear()`, `setMonth()` and `setDate()` methods to set the year, month, date components of the Date object respectively.

For instance, in the following example we have used `setFullYear()` method to change the current date stored in a variable ahead of two year in the future.

#### Example

```js
var d = new Date();
d.setFullYear(d.getFullYear() + 2);
alert(d); // Display future date
```

The output of the above example will look something like this:

Sat Dec 25 2021 18:14:32 GMT+0100 (Central European Standard Time)

Likewise, you can use the `setMonth()` method to set or modify the month part of a Date object.

#### Example

```js
var d = new Date(); // Current date and time
d.setMonth(0); // Sets month to 0, January
document.write(d);
```

The `setMonth()` method require an integer value from 0 to 11, if you set the value of the month greater than 11, the year value of the date object will increment.

In other words, a value of 12 results in the year value increasing by 1, and the month value set to 0, as demonstrated in the following example:

#### Example

```js
var d = new Date(2018, 5, 24); // June 24, 2018
d.setMonth(12); // Sets month to 12, new date will be January 24, 2019
document.write(d);
```

Similarly, you can modify the date part of the date object, like this:

#### Example

```js
var d = new Date(2018, 5, 24); // June 24, 2018
d.setDate(15); // Sets date to 15, new date will be June 15, 2018
document.write(d);
```

The `setDate()` method require an integer value from 1 to 31. Also, if you pass the values greater than the number of days in the month, the month will increment. For example:

#### Example

```js
var d = new Date(2018, 5, 24); // June 24, 2018
d.setDate(36); // Sets day to 36, new date will be July 6, 2018
document.write(d);
```

## Setting the Hours, Minutes and Seconds

Methods for setting the time values are also pretty straight forward. The `setHours()`, `setMinutes()`, `setSeconds()`, `setMilliseconds()` can be used to set the hour, minutes, seconds, and milliseconds part of the Date object respectively.

Each method takes integer values as parameters. Hours range from 0 to 23. Minutes and seconds range from 0 to 59. And milliseconds range from 0 to 999. Here is an example:

#### Example

```js
var d = new Date(2018, 5, 24); // June 24, 2018 00:00:00
d.setHours(8);
d.setMinutes(30);
d.setSeconds(45);
d.setMilliseconds(600);
document.write(d);
```

The output of the above example will look something like the following:

Sun Jun 24 2018 08:30:45 GMT+0200 (Central European Summer Time)

* * *