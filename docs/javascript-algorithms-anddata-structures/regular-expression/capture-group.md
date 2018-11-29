---
id: capture-group
title: Capture Group
---

Capture Group 的特点就是在匹配的基础之上将匹配的内容保存下来，并将保存的内容存放在数组当中。

```js
let str = 'apple banana orange';

let regex1 = /(apple)\s(banana)/;
let regex2 = /apple\sbanana/;

console.log(str.match(regex1));
// return [ 'apple banana', 'apple', 'banana', index: 0, input: 'apple banana orange' ]

console.log(str.match(regex2));
// return [ 'apple banana', index: 0, input: 'apple banana orange' ]
```

其他的基本用法可以阅读下面的文章，这篇文章还提到了 capture group 在 ES2018 中的新 feature：

- [CAPTURING GROUPS](https://flaviocopes.com/javascript-regular-expressions/#capturing-groups)

还可以参考一下 MDN 的文档：

- [(x)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#special-capturing-parentheses)
