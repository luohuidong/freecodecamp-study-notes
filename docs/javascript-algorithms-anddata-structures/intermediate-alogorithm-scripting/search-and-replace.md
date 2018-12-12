---
id: search-and-replace
title: Search and Replace
---

个人思路：

- 先判断 before 字符串是否是大写字母开头，如果是，则将 after 字符串改为大写字母开头。
- 使用 `replace`　进行字符串的替换。

```js
function myReplace(str, before, after) {
  if (before.match(/^[A-Z]/)) {
    after = after.slice(0, 1).toUpperCase() + after.slice(1);
  }

  return str.replace(before, after);
}

myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
```
