Form Validation 

# JavaScript Form Validation

## Understanding Client-Side Validation

Web forms have become an essential part of web applications. It is often used to collect user's information such as name, email address, location, age, and so on. But it is quite possible that some user might not enter the data what you've expected. So to save bandwidth and avoid unnecessary strain on your server resources you can validate the form data on client-side (i.e. user's system) using JavaScript before passing it onto the web server for further processing.

Client-side validation is also helpful in creating better user experience, since it is faster because validation occurs within the user's web browser, whereas server-side validation occurs on the server, which require user's input to be first submitted and sent to the server before validation occurs, also user has to wait for server response to know what exactly went wrong.

In the following section we will take a closer look at how to perform JavaScript form validation and handle any input errors found appropriately and gracefully.

**Note:** Client-side validation is not a substitute or alternative for server-side validation. You should always validate form data on the server-side even if they are already validated on the client-side, because user can disable JavaScript in their browser.
* * *
## Form Validation with JavaScript

The form validation process typically consists of two parts— the _required fields validation_ which is performed to make sure that all the mandatory fields are filled in, and the _data format validation_ which is performed to ensure that the type and format of the data entered in the form is valid.

Well, let's get straight to it and see how this actually works.
* * *
## Creating the HTML Form

Let's first create a simple HTML form that we will validate on client-side using JavaScript when the user clicks on the submit button. Well, let's create an HTML file named "application-form.html" and place the following code in it, then save it somewhere on your system.

#### Example

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Simple HTML Form</title>
    <link rel="stylesheet" href="style.css">
    <script src="validator.js"></script>
</head>
<body>
<form name="contactForm" onsubmit="return validateForm()" action="confirmation.php" method="post">
    <h2>Application Form</h2>
    <div class="row">
        <label>Full Name</label>
        <input type="text" name="name">
        <div class="error" id="nameErr"></div>
    </div>
    <div class="row">
        <label>Email Address</label>
        <input type="text" name="email">
        <div class="error" id="emailErr"></div>
    </div>
    <div class="row">
        <label>Mobile Number</label>
        <input type="text" name="mobile" maxlength="10">
        <div class="error" id="mobileErr"></div>
    </div>
    <div class="row">
        <label>Country</label>
        <select name="country">
            <option>Select</option>
            <option>Australia</option>
            <option>India</option>
            <option>United States</option>
            <option>United Kingdom</option>
        </select> 
        <div class="error" id="countryErr"></div>
    </div>
    <div class="row">
        <label>Gender</label>
        <div class="form-inline">
            <label><input type="radio" name="gender" value="male"> Male</label>
            <label><input type="radio" name="gender" value="female"> Female</label> 
        </div>
        <div class="error" id="genderErr"></div>
    </div>
    <div class="row">
        <label>Hobbies <i>(Optional)</i></label>
        <div class="form-inline">
            <label><input type="checkbox" name="hobbies[]" value="sports"> Sports</label>
            <label><input type="checkbox" name="hobbies[]" value="movies"> Movies</label>
            <label><input type="checkbox" name="hobbies[]" value="music"> Music</label>  
        </div>
    </div>        
    <div class="row">
        <input type="submit" value="Submit">
    </div>
</form>
</body>
</html>
```
* * *
## Building the Form Validation Script

Now we're going to create a JavaScript file that holds our complete validation script.

Well, let's create a JavaScript file named "validator.js" and place the following code inside it, then save it at the same location where you've saved the previous HTML file. Go through each line of the following example code to understand how JavaScript validation works:

#### Example

```javascript
// Defining a function to display error message
function printError(elemId, hintMsg) {
    document.getElementById(elemId).innerHTML = hintMsg;
}

// Defining a function to validate form 
function validateForm() {
    // Retrieving the values of form elements 
    var name = document.contactForm.name.value;
    var email = document.contactForm.email.value;
    var mobile = document.contactForm.mobile.value;
    var country = document.contactForm.country.value;
    var gender = document.contactForm.gender.value;
    var hobbies = [];
    var checkboxes = document.getElementsByName("hobbies[]");
    for(var i=0; i < checkboxes.length; i++) {
        if(checkboxes[i].checked) {
            // Populate hobbies array with selected values
            hobbies.push(checkboxes[i].value);
        }
    }
    
	// Defining error variables with a default value
    var nameErr = emailErr = mobileErr = countryErr = genderErr = true;
    
    // Validate name
    if(name == "") {
        printError("nameErr", "Please enter your name");
    } else {
        var regex = /^[a-zA-Z\s]+$/;                
        if(regex.test(name) === false) {
            printError("nameErr", "Please enter a valid name");
        } else {
            printError("nameErr", "");
            nameErr = false;
        }
    }
    
    // Validate email address
    if(email == "") {
        printError("emailErr", "Please enter your email address");
    } else {
        // Regular expression for basic email validation
        var regex = /^\S+@\S+\.\S+$/;
        if(regex.test(email) === false) {
            printError("emailErr", "Please enter a valid email address");
        } else{
            printError("emailErr", "");
            emailErr = false;
        }
    }
    
    // Validate mobile number
    if(mobile == "") {
        printError("mobileErr", "Please enter your mobile number");
    } else {
        var regex = /^[1-9]\d{9}$/;
        if(regex.test(mobile) === false) {
            printError("mobileErr", "Please enter a valid 10 digit mobile number");
        } else{
            printError("mobileErr", "");
            mobileErr = false;
        }
    }
    
    // Validate country
    if(country == "Select") {
        printError("countryErr", "Please select your country");
    } else {
        printError("countryErr", "");
        countryErr = false;
    }
    
    // Validate gender
    if(gender == "") {
        printError("genderErr", "Please select your gender");
    } else {
        printError("genderErr", "");
        genderErr = false;
    }
    
    // Prevent the form from being submitted if there are any errors
    if((nameErr || emailErr || mobileErr || countryErr || genderErr) == true) {
       return false;
    } else {
        // Creating a string from input data for preview
        var dataPreview = "You've entered the following details: \n" +
                          "Full Name: " + name + "\n" +
                          "Email Address: " + email + "\n" +
                          "Mobile Number: " + mobile + "\n" +
                          "Country: " + country + "\n" +
                          "Gender: " + gender + "\n";
        if(hobbies.length) {
            dataPreview += "Hobbies: " + hobbies.join(", ");
        }
        // Display input data in a dialog box before submitting the form
        alert(dataPreview);
    }
};
```

The value of an individual form field can be accessed and retrieved using the syntax `document.formName.fieldName.value` or `document.getElementsByName(_name_).value`. But, to get the values from a form field that supports multiple selections, like a group of checkboxes, you need to utilize the [loop statement](https://www.tutorialrepublic.com/javascript-tutorial/javascript-loops.php) as shown in the example above (_line no-14 to 21_).

Also, to check whether the format of input data is correct or not we've used the [_regular expressions_](https://www.tutorialrepublic.com/javascript-tutorial/javascript-regular-expressions.php). It is one of the most effective techniques for validating the user inputs.

Furthermore, the above script will also display the data entered by the user in an alert dialog box for preview purpose before submitting the form to the web server.

**Tip:** However, you can validate email format using regular expression. But a user might enter an email that is correctly formatted but does not exist. So for authentic email validation, [send confirmation email](https://www.tutorialrepublic.com/php-tutorial/php-send-email.php) to the user and verify whether the email really exists or not.
* * *
## Adding Style Sheet to Beautify the Form

Finally, create the file named "style.css" and place the following code in it, then save it also at the same location where you've saved the previous two files. These are the style rules to beautify our form.

#### Example

```css
body {
    font-size: 16px;
    background: #f9f9f9;
    font-family: "Segoe UI", "Helvetica Neue", Arial, sans-serif;
}
h2 {
    text-align: center;
    text-decoration: underline;
}
form {
    width: 300px;
    background: #fff;
    padding: 15px 40px 40px;
    border: 1px solid #ccc;
    margin: 50px auto 0;
    border-radius: 5px;
}
label {
    display: block;
    margin-bottom: 5px
}
label i {
    color: #999;
    font-size: 80%;
}
input, select {
    border: 1px solid #ccc;
    padding: 10px;
    display: block;
    width: 100%;
    box-sizing: border-box;
    border-radius: 2px;
}
.row {
    padding-bottom: 10px;
}
.form-inline {
    border: 1px solid #ccc;
    padding: 8px 10px 4px;
    border-radius: 2px;
}
.form-inline label, .form-inline input {
    display: inline-block;
    width: auto;
    padding-right: 15px;
}
.error {
    color: red;
    font-size: 90%;
}
input[type="submit"] {
    font-size: 110%;
    font-weight: 100;
    background: #006dcc;
    border-color: #016BC1;
    box-shadow: 0 3px 0 #0165b6;
    color: #fff;
    margin-top: 10px;
    cursor: pointer;
}
input[type="submit"]:hover {
    background: #0165b6;
}
```

That's all, now open the "application-form.html" file in a web browser and try to fill some data and see how the script respond when an invalid data is entered in a form field.


* * *