---
id: diff-two-arrays
title: Diff Two Arrays
---

个人思路：

- 要找出一个数组当中的元素，是否不存在与另一个数组当中，可以使用 Set 数据结构当中的 `has()` 方法。

```js
function diffArray(arr1, arr2) {
  const arr1Set = new Set(arr1);
  const arr2Set = new Set(arr2);

  const newArr = arr1.filter(element => !arr2Set.has(element))
    .concat(arr2.filter(element => !arr1Set.has(element)));

  // Same, same; but different.
  return newArr;
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```

freeCodeCamp 中级思路及高级思路中，巧妙地用到了 ES6 `includes()` 来判断数组元素是否存在与另一个数组当中。
