---
id: steamroller
title: Steamroller
---

```js
function steamrollArray(arr) {
  let newArr = []

  arr.forEach(element => {
    if(Array.isArray(element)) {
      newArr = newArr.concat(steamrollArray(element))
    } else {
      newArr.push(element)
    }
  })

  return newArr;
}

const result = steamrollArray([1, [2], [3, [[4]]]]);
```
