Dialog Boxes

# Dialog Boxes

In this tutorial you will learn how to create dialog boxes in the JavaScript.

## Creating Dialog Boxes

In JavaScript you can create dialog boxes or popups to interact with the user. You can either use them to notify a user or to receive some kind of user input before proceeding.

You can create three different types of dialog boxes _alert_, _confirm_, and _prompt_ boxes.

The appearance of these dialog boxes is determined by the operating system and/or browser settings, they cannot be modified with the [CSS](https://www.tutorialrepublic.com/css-tutorial/). Also, dialog boxes are modal windows; when a dialog box is displayed the code execution stops, and resumes only after it has been dismissed.

In the following section we will discuss each of these dialog boxes in detail.

## Creating Alert Dialog Boxes

An alert dialog box is the most simple dialog box. It enables you to display a short message to the user. It also includes OK button, and the user has to click this OK button to continue.

You can create alert dialog boxes with the `alert()` method. You've already seen a lot of alert examples in the previous chapters. Let's take a look at one more example:

#### Example

```javascript
var message = "Hi there! Click OK to continue.";
alert(message);
 
/* The following line won't execute until you dismiss previous alert */
alert("This is another alert box.");
```

* * *

## Creating Confirm Dialog Boxes

A confirm dialog box allows user to confirm or cancel an action. A confirm dialog looks similar to an alert dialog but it includes a Cancel button along with the OK button.

You can create confirm dialog boxes with the `confirm()` method. This method simply returns a Boolean value (`true` or `false`) depending on whether the user clicks OK or Cancel button. That's why its result is often assigned to a variable when it is used.

The following example will print some text in the browser depending on which button is clicked.

#### Example

```javascript
var result = confirm("Are you sure?");
 
if(result) {
    document.write("You clicked OK button!");
} else {
    document.write("You clicked Cancel button!");
}
```

* * *

## Creating Prompt Dialog Box

The prompt dialog box is used to prompt the user to enter information. A prompt dialog box includes a text input field, an OK and a Cancel button.

You can create prompt dialog boxes with the `prompt()` method. This method returns the text entered in the input field when the user clicks the OK button, and [`null`](https://www.tutorialrepublic.com/javascript-tutorial/javascript-data-types.php#null) if user clicks the Cancel button. If the user clicks OK button without entering any text, an empty string is returned. For this reason, its result is usually assigned to a variable when it is used.

The following example will print the value entered by you when you click the OK button.

#### Example

```javascript
var name = prompt("What's your name?");
 
if(name.length > 0 && name != "null") {
    document.write("Hi, " + name);
} else {
    document.write("Anonymous!");
}
```

The value returned by the `prompt()` method is always a string. This means if the user enters 10 in the input field, the string "10" is returned instead of the number 10.

Therefore, if you want to use the returned value as a number you must covert it or [cast to Number](https://www.tutorialrepublic.com/javascript-tutorial/javascript-type-conversions.php), like this: `var age = Number(prompt("What's your age?"));`

**Tip:** To display line breaks inside the dialog boxes, use newline character or line feed (`\n`); a backslash followed by the character n.
* * *
