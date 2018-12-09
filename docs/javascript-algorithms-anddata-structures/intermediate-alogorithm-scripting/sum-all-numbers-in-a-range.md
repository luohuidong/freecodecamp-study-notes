---
id: sum-all-numbers-in-a-range
title: Sum All Numbers in a Range
---

个人思路：

1. 对数组中的元素进行从小到大的排序
1. 利用 for 循环计算总和

```js
function sumAll(arr) {
  const newArr = [...arr]
  newArr.sort((a, b) => a-b)

  let sum = 0;

  for (let i = newArr[0]; i <= newArr[1]; i++) {
    sum += i;
  }

  return sum;
}

sumAll([1, 4]);
```

freeCodeCamp 初级思路与中级思路中，都是先找出数组中的最小值与最大值，然后利用 for 循环进行求知。

中级思路中我看到一个比较有意思的东西，就是利用等差数列进行求和。
