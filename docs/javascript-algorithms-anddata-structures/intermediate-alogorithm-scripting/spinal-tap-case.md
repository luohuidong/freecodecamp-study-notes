---
id: spinal-tap-case
title: Spinal Tap Case
---

个人思路：

先看一下 freeCodeCamp 的测试用例

- `"This Is Spinal Tap"`
- `"thisIsSpinalTap"`
- `"The_Andy_Griffith_Show"`
- `"Teletubbies say Eh-oh"`
- `"AllThe-small Things"`

全部都转成 spinal case (Spinal case is all-lowercase-words-joined-by-dashes)

分析一下需要转换的地方有哪些特点：

1. 空格 + 大写字母
1. 小写字母 + 大写字母
1. 下划线 + 大写字母

由于只有三种类型，所以我选择使用正则表达式来解决，将第一种跟第三种情况归为一类，第二种单独一类。

```js
function spinalCase(str) {
  let newStr = ''

  const reg1 = /[\s_]/g;
  newStr = str.replace(reg1, '-')

  const reg2 = /([a-z])([A-Z])/g;
  newStr = newStr.replace(reg2, '$1-$2')

  newStr = newStr.toLowerCase();

  return newStr
}

spinalCase('This Is Spinal Tap');
```
