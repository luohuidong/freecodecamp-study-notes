---
id: grid-container
title: Grid Container
---

本文总结的是 CSS Grid 这一章应用于 grid container 的 CSS 属性。

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

### grid-template-rows

The `grid-template-rows` property specifies the number (and the heights) of the rows in a grid layout.

虽然 `grid-template-rows` 的参数个数表示 grid 的行数，但实际上，grid 行数还是受 gird item 个数和 `gird-template-columns` 的影响。

[grid-template-rows example](https://codepen.io/luohuidong/pen/YRGENq)

从链接中的例子中可以看出，第 2 个 container 的 `grid-template-rows` 定义了 1 行，但是由于 `grid-template-columns` 定义了 3 列，则 5 个 grid item 必定需要 2 行才能容纳得下。因此可以得知 gird 的行数，实际上还是会受 grid item 个数和 `gird-template-columns` 影响。

### repeat()

如果你想给 grid container 定义一百列，或者一百行，这时候在 `grid-template-columns` 或者 `grid-template-rows` 填写 100 个参数明显是不可取的。此时可以使用内置函数 `repeat()`。

Here's an example that would create the 100 row grid, each row at 50px tall.

```css
.container {
  display: grid;
  grid-template-rows: repeat(100, 50px);
}
```

### Grid units

You can use absolute and relative units like `px` and `em` in CSS Grid to define the size of rows and columns. You can use these as well:

- `fr`: sets the column or row to a fraction of the available space.
- `auto`: sets the column or row to the width or height of its content automatically.
- `%`: adjusts the column or row to the percent width of its container.
