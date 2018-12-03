---
id: chunky-monkey
title: Chunky Monkey
---

```js
function chunkArrayInGroups(arr, size) {
  let newArray = []
  while(arr.length !== 0) {
    newArray.push(arr.splice(0, size));
  }
  console.log('newArray', newArray);
  return newArray;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
