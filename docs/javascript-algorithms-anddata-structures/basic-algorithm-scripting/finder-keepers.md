---
id: finder-keepers
title: Finders Keepers
---

```js
function findElement(arr, func) {
  return arr.find(element => func(element));
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```
