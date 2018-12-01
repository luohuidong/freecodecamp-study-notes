---
id: factorialize-a-number
title: Factorialize a Number
---

这个练习是一个阶乘的算法，第一眼看到的时候，首先会想到用递归，但是第一个排除不用的方法也是递归，主要的原因在于递归占资源。如果数据量比较大，那么调用栈所占的资源也就越多。

因此我首先想到的是使用 `for` 循环去完成阶乘算法。

```js
function factorialize(num) {
  let factorial = 1;
  for(let i = num; i > 0; i--) {
    factorial *= i;
  }
  return factorial;
}

factorialize(5);
```

然后我看了一下 freeCodeCamp 给出的解决方式，是利用递归去实现阶乘算法。

```js
function factorialize(num) {
  if (num === 0) { return 1; }
  return num * factorialize(num-1);
}

factorialize(5);
```

既然用递归，那么就可以利用 ES6 中的尾调用优化，关于什么是尾调用优化以及对调用栈的优化是怎样的，可以参考一下 Nicholas C. Zakas *Understanding ECMAScript 6* [Tail Call Optimization](https://leanpub.com/understandinges6/read/#leanpub-auto-tail-call-optimization) 以及阮一峰的《ECMAScript》[尾调用优化](http://es6.ruanyifeng.com/#docs/function#%E5%B0%BE%E8%B0%83%E7%94%A8%E4%BC%98%E5%8C%96)。

下面是使用尾调用优化的阶乘实现方式：

```js
const factorialize = (num, factorial=1) => {
  if (num === 0) {
    return factorial;
  }
  return factorialize(num -1 , factorial * num);
}
```
