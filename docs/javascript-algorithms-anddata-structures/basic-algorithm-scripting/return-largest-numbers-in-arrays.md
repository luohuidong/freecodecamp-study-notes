---
id: return-largest-numbers-in-arrays
title: Return Largest Numbers In Arrays
---

个人解题思路：

- 遍历最外层的数组
- 获取第二层数组中的最大值
- 保存第二层数组中的最大值

具体到代码：

- `map()` 遍历了外层的数组（利用其每轮 return 的数据将组成新的数组的特性）
- `Math.max()` 获取了第二层数组中最大的数
- `reduce()` 遍历了第二层数组（主要是运用它的累加器特性，即 x 保留的是上一轮循环 return 的结构）

```js
function largestOfFour(arr) {
  return arr.map(element => element.reduce((x, y) => Math.max(x, y)))
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

还可以利用 ES6 扩展运算符，连 `reduce` 都省了，使算法更为简洁。

```js
function largestOfFour(arr) {
  return arr.map(element => Math.max(...element))
}
```
