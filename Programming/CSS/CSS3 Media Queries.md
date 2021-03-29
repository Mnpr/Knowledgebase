CSS3 Media Queries

# CSS3 Media Queries

CSS media queries enable you to format your documents to be presented correctly on different size of output devices.

## Media Queries and Responsive Web Design

Media queries allow you to customize the presentation of your web pages for a specific range of devices like mobile phones, tablets, desktops, etc. without any change in markups. A media query consists of a media type and zero or more expressions that match the type and conditions of a particular media features such as device width or screen resolution.

Since media query is a logical expression it can be resolve to either true or false. The result of the query will be true if the media type specified in the media query matches the type of device the document is being displayed on, as well as all expressions in the media query are satisfied. When a media query is true, the related style sheet or style rules are applied to the target device. Here's a simple example of the media query for standard devices.

#### Example

```css
/* Smartphones (portrait and landscape) ---------- */
@media screen and (min-width: 320px) and (max-width: 480px){
    /* styles */
}
/* Smartphones (portrait) ---------- */
@media screen and (max-width: 320px){
    /* styles */
}
/* Smartphones (landscape) ---------- */
@media screen and (min-width: 321px){
    /* styles */
}
/* Tablets, iPads (portrait and landscape) ---------- */
@media screen and (min-width: 768px) and (max-width: 1024px){
    /* styles */
}
/* Tablets, iPads (portrait) ---------- */
@media screen and (min-width: 768px){
    /* styles */
}
/* Tablets, iPads (landscape) ---------- */
@media screen and (min-width: 1024px){
    /* styles */
}
/* Desktops and laptops ---------- */
@media screen and (min-width: 1224px){
    /* styles */
}
/* Large screens ---------- */
@media screen and (min-width: 1824px){
    /* styles */
}
```

**Tip:** Media queries are an excellent way to create responsive layouts. Using media queries you can customize your website differently for users browsing on devices like smart phones or tablets without changing the actual content of the page.

* * *

## Changing Column Width Based on Screen Size

You can use the CSS media query for changing the web page width and related elements to offer the best viewing experience for the user on different devices.

The following style rules will automatically change the width of the container element based on the screen or viewport size. For example, if the viewport width is less than 768 pixels it will cover the 100% of the viewport width, if it is greater than the 768 pixels but less than the 1024 pixels it will be 750 pixels wide, and so on.

#### Example

```css
.container {
    margin: 0 auto;
    background: #f2f2f2;
    box-sizing: border-box;
}
/* Mobile phones (portrait and landscape) ---------- */
@media screen and (max-width: 767px){
    .container {
        width: 100%;
        padding: 0 10px;
    }
}
/* Tablets and iPads (portrait and landscape) ---------- */
@media screen and (min-width: 768px) and (max-width: 1023px){
    .container {
        width: 750px;
        padding: 0 10px;
    }
}
/* Low resolution desktops and laptops ---------- */
@media screen and (min-width: 1024px) {
    .container {
        width: 980px;
        padding: 0 15px;
    }
}
/* High resolution desktops and laptops ---------- */
@media screen and (min-width: 1280px) {
    .container {
        width: 1200px;
        padding: 0 20px;
    }
}
```

**Note:** You can use the CSS3 [box-sizing](https://www.tutorialrepublic.com/css-tutorial/css3-box-sizing.php) property on the elements to create more intuitive and flexible layouts with much less effort.

* * *

## Changing Layouts Based on Screen Size

You can also use the CSS media query for making your multi-column website layout more adaptable and responsive for devices through little customization.

The following style rule will create a two column layout if the viewport size is greater than or equal to 768 pixels, but if less than that it'll be rendered as one column layout.

#### Example

```css
.column {
    width: 48%;
    padding: 0 15px;
    box-sizing: border-box;
    background: #93dcff;
    float: left;
}
.container .column:first-child{
    margin-right: 4%;
}
@media screen and (max-width: 767px){
    .column {
        width: 100%;
        padding: 5px 20px;
        float: none;
    }
    .container .column:first-child{
        margin-right: 0;
        margin-bottom: 20px;
    }
}
```
* * *