Set and Get Cookies

# JavaScript Cookies

Create, Read, Update and Delete a cookie in JavaScript.
* * *
## What is a Cookie

A cookie is a small text file that lets you store a small amount of data (nearly 4KB) on the user's computer. They are typically used for keeping track of information such as user preferences that the site can retrieve to personalize the page when user visits the website next time.

Cookies are an old client-side storage mechanism that was originally designed for use by server-side scripting languages such as PHP, ASP, etc. However, cookies can also be created, accessed, and modified directly using JavaScript, but the process is little bit complicated and messy.

**Tip:** A cookie can be up to 4 KB, including its name and values, cookies that exceed this length are trimmed to fit. Also, each time the browser requests a page to the server, all the data in the cookie is automatically sent to the server within the request.

**Warning:** Don't store sensitive data such as a password or credit card information in cookies since it could potentially be manipulated by the malicious user.
* * *
## Creating a Cookie in JavaScript

In JavaScript, you can create, read, and delete cookies with the `document.cookie` property. This property represents all the cookies associated with a document.

To create or store a new cookie, assign a `_name=value_` string to this property, like this:

document.cookie = "firstName=Christopher";

A cookie value cannot contain semicolons, commas, or spaces. For this reason, you will need to use the JavaScript's built-in function `encodeURIComponent()` to encode the values containing these characters before storing it in the cookie. Likewise, you'll need to use the corresponding `decodeURIComponent()` function when you read the cookie value.

document.cookie = "name=" + encodeURIComponent("Christopher Columbus");

By default, the lifetime of a cookie is the current browser session, which means it is lost when the user exits the browser. For a cookie to persist beyond the current browser session, you will need to specify its lifetime (in seconds) with a `max-age` attribute. This attribute determine how long a cookie can be remain on the user's system before it is deleted, e.g., following cookie will live for 30 days.

document.cookie = "firstName=Christopher; max-age=" + 30\*24\*60*60;

You can also specify the lifetime of a cookie with the `expires` attribute. This attribute takes an exact date (in GMT/UTC format) when the cookie should expire, rather than an offset in seconds.

document.cookie = "firstName=Christopher; expires=Thu, 31 Dec 2099 23:59:59 GMT";

Here's a function that sets a cookie with an optional `max-age` attribute. You can also use the same function to delete a cookie by passing the value `0` for `daysToLive` parameter.

#### Example

```javascript
function setCookie(name, value, daysToLive) {
    // Encode value in order to escape semicolons, commas, and whitespace
    var cookie = name + "=" + encodeURIComponent(value);
    
    if(typeof daysToLive === "number") {
        /* Sets the max-age attribute so that the cookie expires
        after the specified number of days */
        cookie += "; max-age=" + (daysToLive*24*60*60);
        
        document.cookie = cookie;
    }
}
```

By default, a cookie is available to all web pages in the same directory or any subdirectories of that directory. However, if you specify a `path` the cookie is available to all web pages in the specified path and to all web pages in all subdirectories of that path. For example, if the path is set to `/` the cookie is available throughout a website, regardless of which page creates the cookie.

document.cookie = "firstName=Christopher; path=/";

Further, you can use the `domain` attribute if you want a cookie to be available across subdomains. By default, cookies are available only to the pages in the domain they were set in.

If a cookie created by a page on `blog.example.com` sets its `path` attribute to `/` and its `domain` attribute to `example.com`, that cookie is also available to all web pages on `backend.example.com`, `portal.example.com`. However, you cannot share cookies outside of a domain.

document.cookie = "firstName=Christopher; path=/; domain=example.com";

There is also a boolean attribute named `secure`. If this attribute is specified, the cookie will be only be transmitted over a secure (i.e. encrypted) connection such as HTTPS.

document.cookie = "firstName=Christopher; path=/; domain=example.com; secure";

* * *

## Reading a Cookie

Reading a cookie is a slightly more complex because the `document.cookie` property simply returns a string containing _a semicolon and a space_ separated list of all cookies (i.e. `_name=value_` pairs, for example, `firstName=John; lastName=Doe;`). This string doesn't contain the attributes such as `expires`, `path`, `domain`, etc. that may have been set for the cookie.

In order to get the individual cookie from this list, you need to make use of `split()` method to break it into individual `_name=value_` pairs, and search for the specific name, as shown below:

#### Example

```javascript
function getCookie(name) {
    // Split cookie string and get all individual name=value pairs in an array
    var cookieArr = document.cookie.split(";");
    
    // Loop through the array elements
    for(var i = 0; i < cookieArr.length; i++) {
        var cookiePair = cookieArr[i].split("=");
        
        /* Removing whitespace at the beginning of the cookie name
        and compare it with the given string */
        if(name == cookiePair[0].trim()) {
            // Decode the cookie value and return
            return decodeURIComponent(cookiePair[1]);
        }
    }
    
    // Return null if not found
    return null;
}
```

Now we're going to create one more function `checkCookie()` that will check whether the `firstName` cookie is set or not by utilizing the above `getCookie()` function, and if it is set then this function will display a greeting message, and if it is not then this function will prompt user to enter their first name and store it in the cookie using our previously created `setCookie()` function.

#### Example

```javascript
function checkCookie() {
    // Get cookie using our custom function
    var firstName = getCookie("firstName");
    
    if(firstName != "") {
        alert("Welcome again, " + firstName);
    } else {
        firstName = prompt("Please enter your first name:");
        if(firstName != "" && firstName != null) {
            // Set cookie using our custom function
            setCookie("firstName", firstName, 30);
        }
    }
}
```

* * *

## Updating a Cookie

The only way to update or modify a cookie is to create another cookie with the same `name` and `path` as an existing one. Creating a cookie with the same name but with a different path then that of an existing one will add an additional cookie. Here's an example:

#### Example

```javascript
// Creating a cookie
document.cookie = "firstName=Christopher; path=/; max-age=" + 30*24*60*60;

// Updating the cookie
document.cookie = "firstName=Alexander; path=/; max-age=" + 365*24*60*60;
```

* * *

## Deleting a Cookie

To delete a cookie, just set it once again using the same `name`, specifying an empty or arbitrary value, and setting its `max-age` attribute to 0. Remember that if you've specified a `path`, and `domain` attribute for the cookie, you'll also need to include them when deleting it.

#### Example

```javascript
// Deleting a cookie
document.cookie = "firstName=; max-age=0";

// Specifying path and domain while deleting cookie
document.cookie = "firstName=; path=/; domain=example.com; max-age=0";
```

However, to delete a cookie using the `expires` attribute, simply set its value (i.e. the expiration date) to a date that has already passed, as demonstrated below.

document.cookie = "firstName=; path=/; expires=Thu, 01 Jan 1970 00:00:00 GMT";


* * *