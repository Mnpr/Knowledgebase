HTML Tables

# HTML Tables

In this tutorial you will learn how to display tabular data using HTML tables.

## Creating Tables in HTML

HTML table allows you to arrange data into rows and columns. They are commonly used to display tabular data like product listings, customer's details, financial reports, and so on.

You can create a table using the `<table>` element. Inside the `<table>` element, you can use the `<tr>` elements to create rows, and to create columns inside a row you can use the `<td>` elements. You can also define a cell as a header for a group of table cells using the `<th>` element.

The following example demonstrates the most basic structure of a table.

#### Example

```markup
<table>
    <tr>
        <th>No.</th>
        <th>Name</th>
        <th>Age</th>
    </tr>
    <tr>
        <td>1</td>
        <td>Peter Parker</td>
        <td>16</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Clark Kent</td>
        <td>34</td>
    </tr>
</table>
```

Tables do not have any borders by default. You can use the CSS [`border`](https://www.tutorialrepublic.com/css-reference/css-border-property.php) property to add borders to the tables. Also, table cells are sized just large enough to fit the contents by default. To add more space around the content in the table cells you can use the CSS [`padding`](https://www.tutorialrepublic.com/css-reference/css-padding-property.php) property.

The following style rules add a 1-pixel border to the table and 10-pixels of padding to its cells.

#### Example

```css
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 10px;
}
```

By default, borders around the table and their cells are separated from each other. But you can collapse them into one by using the [`border-collapse`](https://www.tutorialrepublic.com/css-reference/css-border-collapse-property.php) property on the `<table>` element.

Also, text inside the `<th>` elements are displayed in bold font, aligned horizontally center in the cell by default. To change the default alignment you can use the CSS [`text-align`](https://www.tutorialrepublic.com/css-reference/css-text-align-property.php) property.

The following style rules collapse the table borders and align the table header text to left.

#### Example

```css
table {
    border-collapse: collapse;
}
th {
    text-align: left;
}
```

Please check out the tutorial on [CSS tables](https://www.tutorialrepublic.com/css-tutorial/css-tables.php) to learn about styling HTML tables in details.

**Note:** Most of the [`<table>`](https://www.tutorialrepublic.com/html-reference/html-table-tag.php) element's attribute such as `border`, `cellpadding`, `cellspacing`, `width`, `align`, etc. for styling table appearances in earlier versions has been dropped in HTML5, so avoid using them. Use CSS to [style HTML tables](https://www.tutorialrepublic.com/css-tutorial/css-tables.php) instead.

* * *

## Spanning Multiple Rows and Columns

Spanning allow you to extend table rows and columns across multiple other rows and columns.

Normally, a table cell cannot pass over into the space below or above another table cell. But, you can use the `rowspan` or `colspan` attributes to span multiple rows or columns in a table.

Let's try out the following example to understand how `colspan` basically works:

#### Example

```markup
<table>
    <tr>
        <th>Name</th>
        <th colspan="2">Phone</th>
    </tr>
    <tr>
        <td>John Carter</td>
        <td>5550192</td>
        <td>5550152</td>
    </tr>
</table>
```

Similarly, you can use the `rowspan` attribute to create a cell that spans more than one row. Let's try out an example to understand how row spanning basically works:

#### Example

```markup
<table>
    <tr>
        <th>Name:</th>
        <td>John Carter</td>
    </tr>
    <tr>
        <th rowspan="2">Phone:</th>
        <td>55577854</td>
    </tr>
    <tr>
        <td>55577855</td>
    </tr>
</table>
```

* * *

## Adding Captions to Tables

You can specify a caption (or title) for your tables using the `<caption>` element.

The `<caption>` element must be placed directly after the opening `<table>` tag. By default, caption appears at the top of the table, but you can change its position using the CSS [`caption-side`](https://www.tutorialrepublic.com/css-reference/css-caption-side-property.php) property.

The following example shows how to use this element in a table.

#### Example

```markup
<table>
    <caption>Users Info</caption>
    <tr>
        <th>No.</th>
        <th>Name</th>
        <th>Age</th>
    </tr>
    <tr>
        <td>1</td>
        <td>Peter Parker</td>
        <td>16</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Clark Kent</td>
        <td>34</td>
    </tr>
</table>
```

* * *

## Defining a Table Header, Body, and Footer

HTML provides a series of tags [`<thead>`](https://www.tutorialrepublic.com/html-reference/html-thead-tag.php), [`<tbody>`](https://www.tutorialrepublic.com/html-reference/html-tbody-tag.php), and [`<tfoot>`](https://www.tutorialrepublic.com/html-reference/html-tfoot-tag.php) that helps you to create more structured table, by defining header, body and footer regions, respectively.

The following example demonstrates the use of these elements.

#### Example

```markup
<table>
    <thead>
        <tr>
            <th>Items</th>
            <th>Expenditure</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Stationary</td>
            <td>2,000</td>
        </tr>
        <tr>
            <td>Furniture</td>
            <td>10,000</td>
        </tr>        
    </tbody>
    <tfoot>
        <tr>
            <th>Total</th>
            <td>12,000</td>
        </tr>
    </tfoot>
</table>
```

**Note:** In HTML5, the `<tfoot>` element can be placed either before or after the `<tbody>` and `<tr>` elements, but must appear after any `<caption>`, `<colgroup>`, and `<thead>` elements.

**Tip:** Do not use tables for creating web page layouts. Table layouts are slower at rendering, and very difficult to maintain. It should be used only to display tabular data.
* * * 