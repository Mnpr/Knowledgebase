Conditionals 

# Conditionals

## JavaScript Conditional Statements

JavaScript also allows you to write code that perform different actions based on the results of a logical or comparative test conditions at run time. This means, you can create test conditions in the form of expressions that evaluates to either `true` or `false` and based on these results you can perform certain actions.

### conditional statements :

*   The **if** statement
*   The **if...else** statement
*   The **if...else if....else** statement
*   The **switch...case** statement

We will discuss each of these statements in detail in the coming sections.

## The `if` Statement

The _if_ statement is used to execute a block of code only if the specified condition evaluates to true. This is the simplest JavaScript's conditional statements and can be written like:
```
if(condition) {  
    _// Code to be executed_  
}
```

The following example will output "Have a nice weekend!" if the current day is Friday:

#### Example

```javascript
var now = new Date();
var dayOfWeek = now.getDay(); // Sunday - Saturday : 0 - 6

if(dayOfWeek == 5) {
    alert("Have a nice weekend!");
}
```

* * *

## The `if...else` Statement

You can enhance the decision making capabilities of your JavaScript program by providing an alternative choice through adding an `else` statement to the` if` statement.

The `if...else` statement allows you to execute one block of code if the specified condition is evaluates to true and another block of code if it is evaluates to false. It can be written, like this:
```
if(condition) {  
    _// Code to be executed if condition is true_  
} else {  
    _// Code to be executed if condition is false_  
}
```
The JavaScript code in the following example will output "Have a nice weekend!" if the current day is Friday, otherwise it will output the text "Have a nice day!".

#### Example

```
var now = new Date();
var dayOfWeek = now.getDay(); // Sunday - Saturday : 0 - 6

if(dayOfWeek == 5) {
    alert("Have a nice weekend!");
} else {
    alert("Have a nice day!");
}
```

* * *

## The `if...else if...else` Statement

The `if...else if...else `a special statement that is used to combine multiple `if...else` statements.
```
if(condition1) {  
    _// Code to be executed if condition1 is true_  
} else if(condition2) {  
    _// Code to be executed if the condition1 is false and condition2 is true_  
} else {  
    _// Code to be executed if both condition1 and condition2 are false_  
}
```
* * *

## The Ternary Operator

The ternary operator provides a shorthand way of writing the _if...else_ statements. The ternary operator is represented by the question mark (`?`) symbol and it takes three operands: a condition to check, a result for `true`, and a result for `false`. Its basic syntax is:

var result = (condition) ? value1 : value2

If the condition is evaluated to true the value1 will be returned, otherwise value2 will be returned. To understand how this operator works, consider the following examples:

#### Example

```javascript
var userType;
var age = 21;
if(age < 18) {
    userType = 'Child';
} else {
    userType = 'Adult';
}
alert(userType); // Displays Adult
```

Using the ternary operator the same code could be written in a more compact way:

#### Example

```javascript
var age = 21;
var userType = age < 18 ? 'Child' : 'Adult';
alert(userType); // Displays Adult
```

As you can see in the above example, since the specified condition evaluated to false the value on the right side of the colon (`:`) is returned, which is the string 'Adult'.

**Tip:** Code written using the ternary operator can be difficult to read sometimes. However, it provides a great way to write compact if-else statements.
* * *
## `Switch...Case` Statements


The `switch..case` statement is an alternative to the `if...else if...else` statement, which does almost the same thing. The `switch...case` statement tests a variable or expression against a series of values until it finds a match, and then executes the block of code corresponding to that match. It's syntax is:
```
switch(x){  
    case value1:  
        // Code to be executed if x === value1  
        break;  
    case value2:  
        // Code to be executed if x === value2  
        break;  
    ...  
    default:  
        // Code to be executed if x is different from all values  
}
```
Consider the following example, which display the name of the day of the week.

#### Example

```js
var d = new Date();
	
switch(d.getDay()) {
	case 0:
		alert("Today is Sunday.");
		break;
	case 1:
		alert("Today is Monday.");
		break;
	case 2:
		alert("Today is Tuesday.");
		break;
	case 3:
		alert("Today is Wednesday.");
		break;
	case 4:
		alert("Today is Thursday.");
		break;
	case 5:
		alert("Today is Friday.");
		break;
	case 6:
		alert("Today is Saturday.");
		break;   
	default:
		alert("No information available for that day.");
		break;
}
```

The `getDay()` method returns the weekday as a number from 0 and 6, where 0 represents Sunday. See the [Date and Time](:/9f0849af2688499ea694fcf1de8dde25)

**Note:** In a _switch...case_ statement, the value of the expression or variable is compared against the case value using the strict equality operator (`===`). That means if `x = "0"`, it doesn't match `case 0:`, because their  are not equal.

The `switch...case` statement differs from the `if...else` statement in one important way. The switch statement executes line by line (i.e. statement by statement) and once JavaScript finds a `case` clause that evaluates to true, it's not only executes the code corresponding to that case clause, but also executes all the subsequent `case` clauses till the end of the `switch` block automatically.

To prevent this you must include a `break` statement after each `case` (as you can see in the above example). The `break` statement tells the JavaScript interpreter to break out of the `switch...case` statement block once it executes the code associated with the first true case.

The `break` statement is however not required for the `case` or `default` clause, when it appears at last in a switch statement. Although, it a good programming practice to terminate the last `case`, or `default` clause in a switch statement with a `break`. It prevents a possible programming error later if another case statement is added to the switch statement.

The `default` clause is optional, which specify the actions to be performed if no `case` matches the switch expression. The `default` clause does not have to be the last clause to appear in a switch statement. Here's an example, where `default` is not the last clause.

#### Example

```js
var d = new Date();

switch(d.getDay()) {
    default: 
        alert("Looking forward to the weekend.");
        break;
    case 6:
        alert("Today is Saturday.");
        break; 
    case 0:
        alert("Today is Sunday.");
}
```

* * *

## Multiple Cases Sharing Same Action

Each case value must be unique within a switch statement. However, different cases don't need to have a unique action. Several cases can share the same action, as shown here:

#### Example

```js
var d = new Date();

switch(d.getDay()) {
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
        alert("It is a weekday.");
        break; 
    case 0:
    case 6:
        alert("It is a weekend day.");
        break;
    default: 
        alert("Enjoy every day of your life.");
}
```
* * *