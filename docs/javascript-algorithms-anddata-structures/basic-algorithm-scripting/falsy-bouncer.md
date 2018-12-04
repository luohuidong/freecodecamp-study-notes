---
id: falsy-bouncer
title: Falsy Bouncer
---

这个练习中，给了一个很关键的提示

> Try converting each value to a Boolean.

所以很自然的就会联想到数组当中的 `filter()` 函数。

```js
function bouncer(arr) {
  const newArr = arr.filter(element => !!element);
  return newArr;
}

bouncer([7, "ate", "", false, 9]);
```
