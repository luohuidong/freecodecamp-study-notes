---
id: truncate-a-string
title: Truncate a String
---

```js
function truncateString(str, num) {
  // Clear out that junk in your trunk
  if (str.length > num) {
    str = str.slice(0 , num) + '...'
  }
  return str;
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```
