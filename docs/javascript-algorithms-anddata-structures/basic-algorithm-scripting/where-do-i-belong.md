---
id: where-do-i-belong
title: Where do I Belong
---r

个人解题思路：

- 数组中所有的元素都是数字，这就很好解决排序的问题了，直接通过 `sort()` 来进行排序即可。
- 排序完之后，可以通过 `indexOf()` 来确定插入的数字，在排序后的数组中的位置。

```js
function getIndexToIns(arr, num) {
  arr.push(num);
  arr.sort((a,b) => a - b);
  const index = arr.indexOf(num);
  return index;
}

getIndexToIns([40, 60], 50);
```

FreeCodeCamp 提供的好几种思路，基本上都是沿着上都是下面的思路：

- 将数字添加到数组中
- 对数组进行排序
- 确定添加数字在数组中的位置。
