---
id: title-case-a-sentence
title: Title Case a Sentence
---

```js
function titleCase(str) {
  let arr = str.split(' ').map(element => {
    if (element.length === 1) {
      return element[0].toUpperCase();
    } else {
      return element[0].toUpperCase() + element.slice(1).toLowerCase();
    }
  })
  return arr.join(' ');
}

titleCase("I'm a little tea pot");
```
