Web Storage

# HTML5 Web Storage

The HTML5's web storage feature lets you store some information locally on the user's computer, similar to cookies, but it is faster and much better than cookies. However, web storage is no more secure than cookies. Please check out the tutorial on [PHP cookies](https://www.tutorialrepublic.com/php-tutorial/php-cookies.php) to learn more about cookies.

The information stored in the web storage isn't sent to the web server as opposed to the cookies where data sent to the server with every request. Also, where cookies let you store a small amount of data (nearly 4KB), the web storage allows you to store up to 5MB of data.

There are two types of web storage, which differ in scope and lifetime:

*   **Local storage** — The local storage uses the `localStorage` object to store data for your entire website on a _permanent basis_. That means the stored local data will be available on the next day, the next week, or the next year unless you remove it.
*   **Session storage** — The session storage uses the `sessionStorage` object to store data on a _temporary basis_, for a single browser window or tab. The data disappears when session ends i.e. when the user closes that browser window or tab.

**Tip:** The HTML5's web storage feature is supported in all major modern web browsers like Firefox, Chrome, Opera, Safari and Internet Explorer 8 and above.

* * *

## The localStorage Object

As stated earlier, the localStorage object stores the data with no expiration date. Each piece of data is stored in a key/value pair. The key identifies the name of the information (like 'first_name'), and the value is the value associated with that key (say 'Peter'). Here's an example:

#### Example

```markup
<script>
// Check if the localStorage object exists
if(localStorage) {
    // Store data
    localStorage.setItem("first_name", "Peter");
    
    // Retrieve data
    alert("Hi, " + localStorage.getItem("first_name"));
} else {
    alert("Sorry, your browser do not support local storage.");
}
</script>
```

### Example explained:

The above JavaScript code has the following meaning:

*   **localStorage.setItem(key, value)** stores the value associated with a key.
*   **localStorage.getItem(key)** retrieves the value associated with the key.

You can also remove a particular item from the storage if it exists, by passing the key name to the `removeItem()` method, like `localStorage.removeItem("first_name")`.

However, if you want to remove the complete storage use the `clear()` method, like `localStorage.clear()`. The `clear()` method takes no arguments, and simply clears all key/value pairs from localStorage at once, so think carefully before you using it.

**Note:** The web storage data (both `localStorage` and `sessionStorage`) will not be available between different browsers, for example the data stored in Firefox browser will not available in Google Chrome, Safari, Internet Explorer or other browsers.

* * *

## The sessionStorage Object

The `sessionStorage` object work in the same way as `localStorage`, except that it stores the data only for one session i.e. the data remains until the user closes that window or tab.

Let's try out the following example to understand how it basically works:

#### Example

```markup
<script>
// Check if the sessionStorage object exists
if(sessionStorage) {
    // Store data
    sessionStorage.setItem("last_name", "Parker");
    
    // Retrieve data
    alert("Hi, " + localStorage.getItem("first_name") + " " + sessionStorage.getItem("last_name"));
} else {
    alert("Sorry, your browser do not support session storage.");
}
</script>
```

* * *