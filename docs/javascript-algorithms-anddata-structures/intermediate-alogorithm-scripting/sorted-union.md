---
id: sorted-union
title: Sorted Union
---

合并的数组里面不能用重复的元素，直接可以利用 Set 数据结构的特性来进行处理。

```js
function uniteUnique(arr, ...rest) {
  const set = new Set(arr.concat(...rest));
  return [...set]
}
uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```
