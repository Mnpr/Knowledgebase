Timer Functions

# Timers

In this tutorial you will learn about timer functions in JavaScript.

## Working with Timers

A timer is a function that enables us to execute a function at a particular time.

Using timers you can delay the execution of code so that it does not get done at the exact moment an event is triggered or the page is loaded. For example, you can use timers to change the advertisement banners on your website at regular intervals, or display a real-time clock, etc. There are two timer functions in JavaScript: `setTimeout()` and `setInterval()`.

The following section will show you how to create timers to delay code execution as well as how to perform one or more actions repeatedly using these functions in JavaScript.
* * *
## Executing Code After a Delay

The `setTimeout()` function is used to execute a function or specified piece of code just once after a certain period of time. Its basic syntax is `setTimeout(_function_, _milliseconds_)`.

This function accepts two parameters: a _function_, which is the function to execute, and an optional _delay_ parameter, which is the number of milliseconds representing the amount of time to wait before executing the function (1 second = 1000 milliseconds). Let's see how it works:

#### Example

```markup
<script>
function myFunction() {
    alert('Hello World!');
}
</script>
 
<button onclick="setTimeout(myFunction, 2000)">Click Me</button>
```

The above example will display an alert message after 2 seconds on click of the button.

**Note:** If the _delay_ parameter is omitted or not specified, a value of `0` is used, that means the specified function is executed "immediately", or, as soon as possible.

* * *

## Executing Code at Regular Intervals

Similarly, you can use the `setInterval()` function to execute a function or specified piece of code repeatedly at fixed time intervals. Its basic syntax is `setInterval(_function_, _milliseconds_)`.

This function also accepts two parameters: a _function_, which is the function to execute, and _interval_, which is the number of milliseconds representing the amount of time to wait before executing the function (1 second = 1000 milliseconds). Here's an example:

#### Example

```markup
<script>
function showTime() {
    var d = new Date();
    document.getElementById("clock").innerHTML = d.toLocaleTimeString();
}
setInterval(showTime, 1000);
</script>
 
<p>The current time on your computer is: <span id="clock"></span></p>
```

The above example will execute the `showTime()` function repeatedly after 1 second. This function retrieves the current time on your computer and displays it in the browser.

* * *

## Stopping Code Execution or Cancelling a Timer

Both `setTimeout()` and `setInterval()` method return an unique ID (a positive integer value, called timer identifier) which identifies the timer created by the these methods.

This ID can be used to disable or clear the timer and stop the execution of code beforehand. Clearing a timer can be done using two functions: `clearTimeout()` and `clearInterval()`.

The `setTimeout()` function takes a single parameter, an ID, and clear a `setTimeout()` timer associated with that ID, as demonstrated in the following example:

#### Example

```markup
<script>
var timeoutID;
 
function delayedAlert() {
  timeoutID = setTimeout(showAlert, 2000);
}
 
function showAlert() {
  alert('This is a JavaScript alert box.');
}
 
function clearAlert() {
  clearTimeout(timeoutID);
}
</script>
 
<button onclick="delayedAlert();">Show Alert After Two Seconds</button>
 
<button onclick="clearAlert();">Cancel Alert Before It Display</button>
```

Similarly, the `clearInterval()` method is used to clear or disable a `setInterval()` timer.

#### Example

```markup
<script>
var intervalID;
 
function showTime() {
    var d = new Date();
    document.getElementById("clock").innerHTML = d.toLocaleTimeString();
}
 
function stopClock() {
    clearInterval(intervalID);
}
 
var intervalID = setInterval(showTime, 1000);
</script>
 
<p>The current time on your computer is: <span id="clock"></span></p>
 
<button onclick="stopClock();">Stop Clock</button>
```

**Note:** You can technically use `clearTimeout()` and `clearInterval()` interchangeably. However, for clarity and code maintainability you should avoid doing so.

* * *