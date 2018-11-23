---
id: flex-item
title: Flex Item
---

本文总结的是 flex item 的 CSS 属性

## flex-shrink

When `flex-shrink` property is used, it allows an item to shrink if the flex container is too small. Items shrink when the width of the parent container is smaller than the combined widths of all the flex items within it.

The `flex-shrink` property takes numbers as values. The higher the number, the more it will shrink compared to the other items in the container. For example, if one item has a `flex-shrink` value of 1 and the other has a `flex-shrink` value of 3, the one with the value of 3 will shrink three times as much as the other.

```css
.item1 {
  flex-shrink: 1;
}

.item2 {
  flex-shrink: 2;
}
```

## flex-grow

The opposite of `flex-shrink` is the `flex-grow` property. The `flex-grow` property controls the size of items when the parent container expands.

If one item has a flex-grow value of 1 and the other has a flex-grow value of 3, the one with the value of 3 will grow three times as much as the other.

```css
.item1 {
  flex-grow: 1;
}

.item2 {
  flex-grow: 2;
}
```

## flex-basis

The `flex-basis` property specifies the initial size of the item before CSS makes adjustments with `flex-shrink` or `flex-grow`.

The units used by the `flex-basis` property are the same as other size properties (`px`, `em`, `%`, etc.). The value `auto` sizes items based on the content.

## flex

There is a shortcut available to set several `flex properties` at once. The `flex-grow`, `flex-shrink`, and `flex-basis` properties can all be set together by using the `flex` property.

For example, `flex: 1 0 10px;` will set the item to `flex-grow: 1;`, `flex-shrink: 0;`, and `flex-basis: 10px;`.

The default property settings are `flex: 0 1 auto;`.

## order

The `order` property is used to tell CSS the order of how flex items appear in the flex container. By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.

## align-self

This property allows you to adjust each item's alignment individually, instead of setting them all at once. This is useful since other common adjustment techniques using the CSS properties `float`, `clear`, and `vertical-align` do not work on flex items.

`align-self` accepts the same values as `align-items` and will override any value set by the `align-items` property.

Property Values:

- `flex-start`
- `flex-end`
- `center`
- `stretch`(default): stretch the items to fill the flex container. For example, rows items are stretched to fill the flex container top-to-bottom.
- `baseline`: align items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.
