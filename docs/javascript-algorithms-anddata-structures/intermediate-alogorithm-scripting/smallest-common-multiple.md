---
id: smallest-common-multiple
title: Smallest Common Multiple
---

```js
/**
 * 求两个数的最小公倍数
 * @param {number} num1
 * @param {number} num2
 */
function smallestCommonsOfTwoNumber (num1, num2) {
  let max = num1 < num2 ? num1 : num2

  for (let i = 2; i <= max; i++) {
    if (num1 % i === 0 && num2 % i === 0) {
      return i * smallestCommonsOfTwoNumber(num1 / i, num2 / i)
    }
  }

  return num1 * num2
}

/**
 * 求在一定范围内的所有数的最小公倍数
 * @param {array} arr
 */
function smallestCommons(arr) {
  // 现将数组的元素从小到大排序
  const copyArr = [...arr];
  copyArr.sort((a, b) => a-b);

  // 获取一定范围连续的数字的数组
  let allNumArr = [];
  for(let i = copyArr[0]; i <= copyArr[1]; i++) {
    allNumArr.push(i);
  }

  // 先取数组中的前两个数字的最小公倍数，然后再获取这个公倍数与下一个数组元素的最小公倍数
  // 如此循环计算，即可获取一定范围之内所有数字的最小公倍数
  const result = allNumArr.reduce((a, b) => smallestCommonsOfTwoNumber(a, b))

  return result;
}


smallestCommons([1,5]);
```
