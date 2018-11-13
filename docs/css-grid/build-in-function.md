---
id: build-in-function
title: build-in function
---

本文总结的是应用于 `grid-template-columns` 和 `grid-template-rows` 这两个属性的内置函数。

## repeat()

When you used `grid-template-columns` and `grid-template-rows` to define the structure of a grid, you entered a value for each row or column you created.

Lets say you want a grid with 100 rows of the same height. It isn't very practical to insert 100 values individually. Fortunately, there's a better way - by using the `repeat` function to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat.

Here's an example that would create the 100 row grid, each row at 50px tall.

```css
.container {
  display: gird;
  grid-template-columns: repeat(100, 50px);
}
```

You can also repeat multiple values with the repeat function, and insert the function amongst other values when defining a grid structure. Here's what I mean:

```css
.container {
  display: grid;
  grid-template-columns: repeat(2, 1fr 50px) 20px;
}
```

This translates to:

```css
.container {
  display: grid;
  grid-template-columns: 1fr 50px 1fr 50px 20px;
}
```

## minmax()

It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. Here is an example:

```css
.container {
  display: grid;
  grid-template-columns: 100px minmax(50px, 200px);
}
```

In the code above, grid-template-columns is set to create two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px.
