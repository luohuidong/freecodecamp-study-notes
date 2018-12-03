---
id: falsy-bouncer
title: Falsy Bouncer
---

```js
function bouncer(arr) {
  const newArr = arr.filter(element => !!element);
  return newArr;
}

bouncer([7, "ate", "", false, 9]);
```
