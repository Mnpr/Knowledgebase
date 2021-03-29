Math Operations

# Math Operations

In this tutorial you will learn how to perform math operations in JavaScript.

## Using the Math Object

The JavaScript Math object provides a number of useful properties and methods for performing mathematical tasks like, generating random numbers, rounding numbers, obtaining values such as PI and performing calculation, and so on. It also includes methods for performing mathematical task that are normally impossible or too complex to perform using standard [mathematical operators](https://www.tutorialrepublic.com/javascript-tutorial/javascript-operators.php#arithmetic) (`+`, `-`,`*`, and `/`) such as calculating sine or cosine values.

## The Math.PI Property

The `Math.PI` property represents the ratio of the circumference of a circle to its diameter. PI (`π`) is a mathematical constant, which is approximately 3.14159: `Math.PI = π ≈ 3.14159`

Here is an example that calculates the area of a circle using the Math.PI property.

#### Example

```javascript
// Printing PI value
document.write(Math.PI);  // Prints: 3.141592653589793
 
// Function to calculate circle area
function calculateCircleArea(radius){
    var area = (Math.PI) * radius * radius;
    return area;
}
 
document.write(calculateCircleArea(5));  // Prints: 78.53981633974483
document.write(calculateCircleArea(10));  // Prints: 314.1592653589793
```

**Note:** The Math object is a built-in JavaScript object so its properties and methods can be accessed directly. You'll never need to create a Math object, because it is automatically created by the JavaScript interpreter.

* * *

## Getting the Absolute Value

The `Math.abs()` method is used to calculate the absolute (positive) value of a number. Therefore, -1 is returned as 1, -5 as 5, and so on. Here is an example:

#### Example

```javascript
document.write(Math.abs(-1));  // Prints: 1
document.write(Math.abs(1));  // Prints: 1
document.write(Math.abs(-5));  // Prints: 5
document.write(Math.abs(-10.5));  // Prints: 10.5

```

* * *

## Generating a Random Number

The `Math.random()` method is used to generate a floating-point random number in the range from `0` inclusive up to but not including `1`. However, if you want a random integer between zero and an integer higher than one, you could use the following solution:

#### Example

```javascript
document.write(Math.random());  // Expected output: a number between 0 and 1
 
// Function to create random integer 
function getRandomInt(max) {
    return Math.floor(Math.random() * max);
}
 
document.write(getRandomInt(3));  // Expected output: 0, 1 or 2
document.write(getRandomInt(1));  // Expected output: 0
```

* * *

## Calculating the Square Root of a Number

The `Math.sqrt()` method is used to calculate the square root of a number: `Math.sqrt(_x_) = _x_`

If the number is negative, [`NaN`](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php#number) is returned. Here is an example:

#### Example

```javascript
document.write(Math.sqrt(4));  // Prints: 2
document.write(Math.sqrt(16));  // Prints: 4
document.write(Math.sqrt(0.25));  // Prints: 0.5
document.write(Math.sqrt(-9));  // Prints: NaN
 
/* Function to calculate hypotenuse.
Hypotenuse is the longest side of a right-angled triangle. */
function calculateHypotenuse(a, b) {
    return Math.sqrt((a * a) + (b * b));
}
 
document.write(calculateHypotenuse(3, 4));  // Prints: 5
document.write(calculateHypotenuse(5, 12));  // Prints: 13
```

* * *

## Rounding Numbers

The JavaScript Math object provides few methods to round numbers, each one has its own purpose. The following section will describe these methods in detials.

### The `ceil()` Method

The `Math.ceil()` method rounds a number up to the next highest integer. So, 3.5 becomes 4, -5.7 becomes -5 (because -5 is greater than -6). Here's an example:

#### Example

```javascript
document.write(Math.ceil(3.5));  // Prints: 4
document.write(Math.ceil(-5.7));  // Prints: -5
document.write(Math.ceil(9.99));  // Prints: 10
document.write(Math.ceil(-9.99));  // Prints: -9
document.write(Math.ceil(0));  // Prints: 0
```

### The `floor()` Method

The `Math.floor()` method rounds a number down to the next lowest integer. So, 3.5 becomes 3, -5.7 becomes -6 (because -6 is lesser than -5). Here's an example:

#### Example

```javascript
document.write(Math.floor(3.5));  // Prints: 3
document.write(Math.floor(-5.7));  // Prints: -6
document.write(Math.floor(9.99));  // Prints: 9
document.write(Math.floor(-9.99));  // Prints: -10
document.write(Math.floor(0));  // Prints: 0
```

### The `round()` Method

The `Math.round()` method rounds a number to the nearest integer in such a way that if the decimal part is `.5` or greater, number is rounded up, otherwise rounded down. So, 3.5 becomes 4, -5.7 becomes -6, 4.49 becomes 4, and so on. Here's an example:

#### Example

```javascript
document.write(Math.round(3.5));  // Prints: 4
document.write(Math.round(-5.7));  // Prints: -6
document.write(Math.round(7.25));  // Prints: 7
document.write(Math.round(4.49));  // Prints: 4
document.write(Math.round(0));  // Prints: 0
```

* * *

## Finding the Largest and Smallest Numbers

The `Math.max()` and `Math.min()` methods is used to find which number is the largest or smallest in a group of numbers, respectively. Here's an example:

#### Example

```javascript
document.write(Math.max(1, 3, 2));  // Prints: 3
document.write(Math.max(-1, -3, -2));  // Prints: -1
 
document.write(Math.min(1, 3, 2));  // Prints: 1
document.write(Math.min(-1, -3, -2));  // Prints: -3
```

You can also find the maximum or minimum value within an array or an array-like object using the `apply()` method, as shown in the following example:

#### Example

```javascript
var numbers = [1, 3, 2];
 
document.write(Math.max.apply(null, numbers));  // Prints: 3
document.write(Math.min.apply(null, numbers));  // Prints: 1
```

There is even simpler way to do this. In ECMAScript 6 you can accomplish the same thing using the new [spread operator](https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php#spread-operator) (`...`), as shown in example below:

#### Example

```javascript
var numbers = [1, 3, 2];
 
document.write(Math.max(...numbers));  // Prints: 3
document.write(Math.min(...numbers));  // Prints: 1
```

* * *

## Raising Numbers to a Power

The `Math.pow()` method is used to raise a number to a specified power.

The expression `Math.pow(_x_, _y_)`—equivalent to mathmatically `xy`—shows how many times the _base_ `_x_` is multiplied by the _exponent_ `_y_`. Here's an example:

#### Example

```javascript
document.write(Math.pow(3, 2));  // Prints: 9
document.write(Math.pow(0, 1));  // Prints: 0
document.write(Math.pow(5, -2));  // Prints: 0.04
document.write(Math.pow(16, 0.5));  // Prints: 4 (square root of 4)
document.write(Math.pow(8, 1/3));  // Prints: 2 (cube root of 8)
```

A positive exponent indicates multiplication (52 = 5 x 5 = 25), a negative exponent indicates division (5-2 = 1/52 = 0.04), whereas a fractional exponent indicates a root of the base.

* * *

## Performing Trigonometric Operations

The JavaScript's Math object also provides several trigonometric methods such as `sin()`, `cos()`, `tan()` to perform trigonometric operations. These methods work in radians, so you need to multiply any degree measurements by `π/180` before using them.

Since, pi radians are equal to 180 degrees: `π rad = 180°`. Therefore, π/2 radians is equal 90 degrees, π/3 radians is equal to 60 degrees, and so on. Here's an example:

#### Example

```javascript
document.write(Math.sin(0 * Math.PI / 180));  // Prints: 0
document.write(Math.sin(90 * Math.PI / 180));  // Prints: 1
document.write(Math.cos(0 * Math.PI / 180));  // Prints: 1
document.write(Math.cos(180 * Math.PI / 180));  // Prints: -1
document.write(Math.tan(0 * Math.PI / 180));  // Prints: 0
```
* * *