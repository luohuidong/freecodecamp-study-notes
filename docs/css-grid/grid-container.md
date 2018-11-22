---
id: grid-container
title: Grid Container
---

本文总结的是 CSS Grid 这一部分与 grid container 相关的 CSS 属性。

## Grid Container

Turn any HTML element into a grid container by setting its `display` property to `grid`.

```html
<style>
  .container {
    display: grid;
  }
</style>

<div class="container">

</div>
```

**Note**

Turning an element into a grid only affects the behavior of its direct descendants. So by turning a direct descendant into a grid, you have a grid within a grid.

## Define the structure of the grid

### grid-template-columns

To add some columns to the grid, use the `grid-template-columns` property on a grid container

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

The number of parameters given to the grid-template-columns property indicates the number of columns in the grid, and the value of each parameter indicates the width of each column.

参考资料：

- [Add Columns with grid-template-columns](https://learn.freecodecamp.org/responsive-web-design/css-grid/add-columns-with-grid-template-columns/)


### grid-template-rows

The `grid-template-rows` property specifies the number (and the heights) of the rows in a grid layout.

虽然 `grid-template-rows` 的参数个数表示 grid 的行数，但实际上，grid 行数还是受 gird item 个数和 `gird-template-columns` 的影响。

[grid-template-rows example](https://codepen.io/luohuidong/pen/YRGENq)

从链接中的例子中可以看出，第 2 个 container 的 `grid-template-rows` 定义了 1 行，但是由于 `grid-template-columns` 定义了 3 列，则 5 个 grid item 必定需要 2 行才能容纳得下。因此可以得知 gird 的行数，实际上还是会受 grid item 个数和 `gird-template-columns` 影响。

参考资料：

- [Add Rows with grid-template-rows](https://learn.freecodecamp.org/responsive-web-design/css-grid/add-rows-with-grid-template-rows)
- [CSS grid-template-rows Property](https://www.w3schools.com/cssref/pr_grid-template-rows.asp)

### repeat()

如果你想给 grid container 定义一百列，或者一百行，这时候在 `grid-template-columns` 或者 `grid-template-rows` 填写 100 个参数明显是不可取的。此时可以使用内置函数 `repeat()`。

Here's an example that would create the 100 row grid, each row at 50px tall.

```css
.container {
  display: grid;
  grid-template-rows: repeat(100, 50px);
}
```

参考资料：

- [Reduce Repetition Using the repeat Function](https://learn.freecodecamp.org/responsive-web-design/css-grid/reduce-repetition-using-the-repeat-function/)

### Grid units

You can use absolute and relative units like `px` and `em` in CSS Grid to define the size of rows and columns.

You can use these as well:

- `fr`: sets the column or row to a fraction of the available space.
- `auto`: sets the column or row to the width or height of its content automatically.
- `%`: adjusts the column or row to the percent width of its container.

仅仅只是看 `fr` 作用描述可能不太好理解，举一个简单的例子来解释一下:

```css
.container {
  display: grid;
  grid-template-columns: 50px 2fr 1fr;
}
```

上面的例子中，第一列为 50px 宽度，剩余的空间会被分成 3 份，其中，第 2 列占据了 2 份，而第 3 列占据了 1 份。

参考资料：

- [Use CSS Grid units to Change the Size of Columns and Rows](https://learn.freecodecamp.org/responsive-web-design/css-grid/use-css-grid-units-to-change-the-size-of-columns-and-rows/)

## Grid Gap

### grid-column-gap

To add a gap between the columns, use the grid-column-gap property like this:

```css
.container {
  display: grid;
  grid-template-columns: auto auto;
  grid-column-gap: 10px;
}
```

This creates 10px of empty space between all of our columns.

参考资料：

- [Create a Column Gap Using grid-column-gap](https://learn.freecodecamp.org/responsive-web-design/css-grid/create-a-column-gap-using-grid-column-gap/)
- [CSS grid-column-gap Property](https://www.w3schools.com/cssref/pr_grid-column-gap.asp)

### grid-row-gap

The `grid-row-gap` property defines the size of the gap between the rows in a grid layout.

```css
.container {
  display: grid;
  grid-row-gap: 50px;
}
```

### grid-gap

The `grid-gap` property defines the size of the gap between the rows and columns in a grid layout, and is a shorthand property for `grid-row-gap` and `grid-column-gap`.

If `grid-gap` has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.

```css
.container {
  display: grid;
  grid-template-columns: auto auto;
  grid-gap: 50px;
}
```

## Align All Items

### justify-items

使用 `justify-self` 可以对单个 grid item 中的内容进行水平方向的对齐操作。如果想对所有的 grid container 中所有 item 的内容进行水平方向的操作，可以使用 `justify-items`，该属性接收的值与 `justify-self` 相同。

参考资料：

- [justify-items](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items)

### align-items

使用 `align-self` 可以对单个 grid item 内容进行垂直方向的对齐操作。如果想对所有的 grid container 中所有的 item 内容进行垂直方向的操作，可以使用 `align-items`，该属性接收的值与 `align-self` 相同。

参考资料：

- [align-items](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items)
