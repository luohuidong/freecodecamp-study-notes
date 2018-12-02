---
id: repeat-a-string
title: Repeat a String
---

个人解题思路：

- 重复字符串，并保存在数组中
- 将数组转化为字符串

```js
function repeatStringNumTimes(str, num) {
  let repeatStrArray = [];
  for (let i = 0; i < num; i++) {
    repeatStrArray.push(str)
  }

  return repeatStrArray.join('');
}

repeatStringNumTimes("abc", 3);
```

FreeCodeCamp 在中级解题思路中，使用了递归。在高级解题思路中，使用了 `str.repeat()` 函数。
