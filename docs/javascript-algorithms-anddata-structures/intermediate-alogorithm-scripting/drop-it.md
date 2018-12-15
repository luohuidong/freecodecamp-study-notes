---
id: drop-it
title: Drop it
---

```js
function dropElements(arr, func) {
  const index = arr.findIndex(element => func(element));
  const newArr = index !== -1 ? arr.slice(index) : [];
  return newArr;
}

dropElements([1, 2, 3], function(n) {return n < 3; });
```
