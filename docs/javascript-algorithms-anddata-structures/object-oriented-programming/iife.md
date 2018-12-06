---
id: iife
title: IIFE
---

## Immediately Invoked Function Expression (IIFE)

IIFE 是一个定义之后立即执行的函数，形式如下：

```js
(function () {
    statements
})();
```

IIFE 有两个特点：

- 外部无法访问 IIFE 中定义的变量。
- IIFE 中定义的变量不会污染全局。

另外 IIFE 通常用于将相关的功能封装在一个对象或者模块 (module) 当中。这个也是 Nodejs module 的核心思想。

参考资料：

- [Medium: Mastering Immediately-invoked Function Expressions](https://medium.com/@vvkchandra/essential-javascript-mastering-immediately-invoked-function-expressions-67791338ddc6)
- [MDN: IIFE](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
- [FreeCodeCamp: Understand the Immediately Invoked Function Expression (IIFE)](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming/understand-the-immediately-invoked-function-expression-iife)
- [FreeCodeCamp: Use an IIFE to Create a Module](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming/use-an-iife-to-create-a-module)
