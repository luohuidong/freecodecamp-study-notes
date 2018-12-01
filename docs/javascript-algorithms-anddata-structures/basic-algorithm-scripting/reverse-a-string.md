---
id: reverse-a-string
title: Reverse a String
---

这个知识点的思路并不难，主要步骤：

- 将字符串转换为数组
- 用 `reverse()` 处理数组
- 将数组转换成字符串

有问题的地方在于 freeCodeCamp 给出的提示是利用 `split()` 去分离字符串中的每个字符。这个其实处理有缺陷，更好的处理方式可以参考 [stack overflow](https://stackoverflow.com/questions/4547609/how-do-you-get-a-string-to-a-character-array-in-javascript/34717402#34717402) 中给出的处理方法。

究竟为啥用 `split()` 去处理不妥，链接中有解释。

这个 stack overflow 的答案给出的是利用 ES2015 的新特性去处理，主要有三种方式：

- 利用扩展运算符
- 利用 `Array.from()` 处理
- 利用 RegExp 中的 `u` flag
