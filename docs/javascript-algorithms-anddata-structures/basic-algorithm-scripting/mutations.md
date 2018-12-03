---
id: mutations
title: Mutations
---

```js
function mutation(arr) {
  const firstElement = arr[0].toLowerCase();
  const secondElement = arr[1].toLowerCase();

  for(let i = 0; i < secondElement.length; i++) {
    if (firstElement.indexOf(secondElement[i]) < 0) {
      return false;
    }
  }
  return true;
}

mutation(["hello", "hey"]);
```
