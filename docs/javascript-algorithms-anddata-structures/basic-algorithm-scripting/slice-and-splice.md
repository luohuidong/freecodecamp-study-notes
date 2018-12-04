---
id: slice-and-splice
title: Slice and Splice
---

```js
function frankenSplice(arr1, arr2, n) {
  const newArr = arr2.slice();

  for (let i = 0; i < arr1.length; i++) {
    newArr.splice(n+i, 0, arr1[i]);
  }

  return newArr;
}

frankenSplice([1, 2, 3], [4, 5, 6], 1);
``` 
