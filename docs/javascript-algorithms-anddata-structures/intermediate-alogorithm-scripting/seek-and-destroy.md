---
id: seek-and-destroy
title: Seek and Destroy
---

个人思路：

```js
function destroyer(arr, ...destroyValue) {
  const destroyValueSet = new Set(destroyValue)

  const newArr = arr.filter(element => !destroyValueSet.has(element))

  return newArr;
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```

freeCodeCamp 中的高级思路非常简洁，如下：

```js
const destroyer = (arr, ...args) => arr.filter(i => !args.includes(i));
```
