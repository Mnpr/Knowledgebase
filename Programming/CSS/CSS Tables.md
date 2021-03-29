CSS Tables

# CSS Tables

Tables are commonly used to present tabular data.

## Styling Tables with CSS

When you build an [HTML table](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-tables.php) without any styles or attributes, browsers display them without any border. Styling a table with CSS can greatly improve its appearance.

The following sections will show you how to control the layout and presentation of the table elements using CSS to create elegant and consistent tables.

## Adding Borders to Tables

The CSS [`border`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-property.php) property is the best way to define the borders for the tables.

The following example will set a black border for the [`<table>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-table-tag.php), [`<th>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-th-tag.php), and [`<td>`](https://www.tutorialrepublic.com/css-tutorial/../html-reference/html-td-tag.php) elements.

#### Example

```css
table, th, td {
    border: 1px solid black;
}
```

* * *

## Collapsing Table Borders

If you've seen the output of the previous example, you've noticed every table cell has separate borders as well as there is some space between the borders of adjacent table cells. It happens because table cell borders are separated by default. But, you can collapse the separate table borders into one by using the [`border-collapse`](https://www.tutorialrepublic.com/css-reference/css-border-collapse-property.php) property on the `<table>` element:

The style rules in the following example will collapse the table cell borders as well as apply the one pixel black border on the table and table cell elements.

#### Example

```css
table {
    border-collapse: collapse;
}
table, th, td {
    border: 1px solid black;
}
```

You can also remove the space between the table cell borders through setting the value of CSS [`border-spacing`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-border-spacing-property.php) property to 0. However, it only removes the space but do not merge the borders like when you set the `border-collapse` to `collapse`.

**Note:** If a [`<!DOCTYPE>`](https://www.tutorialrepublic.com/css-tutorial/../html-tutorial/html-doctypes.php) is not specified in the HTML document, the `border-collapse` CSS property may produce unexpected results.

* * *

## Adjusting Space inside Tables

By default, the browser creates the table cells just large enough to contain the data in the cells. To add more space around the content in the table cells you can use the CSS `padding` property, like this:

#### Example

```css
th, td {
    padding: 15px;
}
```

You can also adjust the spacing between the borders of the cells using the CSS [`border-spacing`](https://www.tutorialrepublic.com/css-reference/css-border-spacing-property.php) property, if the borders of your table are separated (which is default).

The following style rules apply the spacing of 10 pixels between all borders within a table:

#### Example

```css
table {
    border-spacing: 10px;
}
```

* * *

## Controlling the Table Layout

By default a table expands and contracts to accommodate the data contained inside it. As data fills inside the table, it continues to expand as long as there is space. Sometimes, however, it is necessary to set a fixed width for the table in order to manage the layout.

You can do this with the help of CSS `table-layout` property. This property defines the algorithm to be used to layout the table cells, rows, and columns. This property takes one of two values:

*   **auto** — Use an automatic table layout algorithm. With this algorithm, the widths of the table and its cells are adjusted to fit the content. This is default.
*   **fixed** — Use the fixed table layout algorithm. With this algorithm, the horizontal layout of the table does not depend on the contents of the cells; it only depends on the table's width, the width of the columns, and borders or cell spacing.

The style rules in the following example indicate that the table is laid out using the fixed layout algorithm and has a fixed width of 300 pixels.

#### Example

```css
table {
    width: 300px;
    table-layout: fixed;
}
```

Without fixed value of the `table-layout` property, on large tables, users won't see any part of the table until the browser has rendered the whole table.

**Tip:** You can optimize table rendering performance by specifying the table-layout property. Fixed value of this property causes the table to be rendered one row at a time, providing users with information at a faster pace.

* * *

## Handling Empty Cells

The `empty-cells` CSS property controls the rendering of the borders and backgrounds of cells that have no visible content in a table that's using the separated borders model.

This property can take one of the three values: `show`, `hide` or [`inherit`](https://www.tutorialrepublic.com/css-tutorial/../definitions.php#inherit).

The following style rule hides empty cells in the table element.

#### Example

```css
table {
    border-collapse: separate;
    empty-cells: hide;
}
```

* * *

## Controlling the Position of Table Caption

The `caption-side` CSS property sets the vertical position of a table caption box.

The following style rule positions the table captions below their parent table. However, to change the horizontal alignment of the caption text, you can use the [`text-align`](https://www.tutorialrepublic.com/css-tutorial/../css-reference/css-text-align-property.php) property.

#### Example

```css
caption {
    caption-side: bottom;
}
```
* * *