---
id: everything-be-true
title: Everything Be True
---

```js
function truthCheck(collection, pre) {
  const result = collection.every(element => !!element[pre])
  return result;
}

truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex");
```
