---
id: missing-letters
title: Missing letters
---

个人思路：

- 找出参数的第一个字母，在 26 个字母字符串当中的索引。
- 参数和索引开始的 26 个字母字符串，逐个字符进行等值比较，发现不同则返回参数中不同的字符。

```js
function fearNotLetter(str) {
  const allLetters = "abcdefghijklmnopqrstuvwxyz";
  const strArr = [...str];
  const firstLetterIndex = allLetters.indexOf(strArr[0])

  let missingLetter

  for (let i = 0; i < strArr.length; i++) {
    if (strArr[i] !== allLetters[i + firstLetterIndex]) {
      missingLetter = allLetters[i + firstLetterIndex]
      break;
    }
  }

  return missingLetter;
}

fearNotLetter("abce");
```
