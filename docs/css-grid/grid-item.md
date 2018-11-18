---
id: grid-item
title: Grid Item
---

本文总结的是 CSS Grid 这一部分 与 grid item 相关的 CSS 属性。

## grid-column

The `grid-column` property specifies a grid item's size and location in a grid layout, and is a shorthand property for `grid-column-start` and `grid-column-end`.

```css
.item {
  grid-column: 1 / 3;
}
```

参考资料：

- [Use grid-column to Control Spacing](https://learn.freecodecamp.org/responsive-web-design/css-grid/use-grid-column-to-control-spacing/)
- [CSS grid-column Property](https://www.w3schools.com/cssref/pr_grid-column.asp)
- [CSS grid-column-start Property](https://www.w3schools.com/cssref/pr_grid-column-start.asp)
- [CSS grid-column-end Property](https://www.w3schools.com/cssref/pr_grid-column-end.asp)

## grid-row

The grid-row property specifies a grid item's size and location in a grid layout, and is a shorthand property for the `grid-row-start` and `grid-row-end`.

```css
.item {
  grid-row: 2 / 4;
}
```

参考资料：

- [CSS grid-row Property](https://www.w3schools.com/cssref/pr_grid-row.asp)
- [CSS grid-row-start Property](https://www.w3schools.com/cssref/pr_grid-row-start.asp)
- [CSS grid-row-end Property](https://www.w3schools.com/cssref/pr_grid-row-end.asp)

## Align an item

### justify-self

In CSS Grid, the content of each item is located in a box which is referred to as a cell. You can align the content's position within its cell horizontally using the justify-self property on a grid item.

By default, this property has a value of stretch, which will make the content fill the whole width of the cell.

Values:

- stretch: makes the content fill the whole width of the cell.
- start: aligns the content at the left of the cell.
- center: aligns the content in the center of the cell.
- end: aligns the content at the right of the cell.

参考资料：

- [Align an Item Horizontally using justify-self](https://learn.freecodecamp.org/responsive-web-design/css-grid/align-an-item-horizontally-using-justify-self/)
- [justify-self](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-self)

### align-self

Just as you can align an item horizontally, there's a way to align an item vertically as well. To do this, you use the `align-self` property on an item. This property accepts all of the same values as `justify-self`.
