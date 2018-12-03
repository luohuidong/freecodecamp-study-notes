---
id: where-do-i-belong
title: Where do I Belong
---

```js
function getIndexToIns(arr, num) {
  arr.push(num);
  arr.sort((a,b) => a - b);
  const index = arr.indexOf(num);
  return index;
}

getIndexToIns([40, 60], 50);
```
