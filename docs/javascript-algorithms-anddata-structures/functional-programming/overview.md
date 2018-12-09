---
id: overview
title: Functional Programming
---

![functional programming](https://cdn.nlark.com/yuque/0/2018/png/103970/1544358516388-5ef63bfb-fdbf-4653-a4f8-02499cf97e1e.png)

## 函数式编程

函数式编程是一种编程风格，用简单的、不依赖于外界变量、对外界作用域没有影响的函数去处理问题。

函数式编程的三大原则：

1. 它是一个独立的函数：它的内部执行，并不依赖外部。

    函数的内部并不会直接去引用外部的变量，要达到这个目的，就需要函数明确定义需要的参数。

1. 它是一个纯函数：同样的输入，必定得到同样的输出。

1. 它没有副作用：函数的处理过程，并不会对程序的状态产生任何的改变。

    函数内部的处理，并不改变外部的变量。例如处理一个传进来的数组，那么函数的整个处理过程，都不会改变这个数组。

## 函数式编程的好处

1. 让函数的处理过程容易进行测试。
1. 通过明确的参数定义，能非常明确地知道这个函数输入需要什么，输出结果依赖什么。
1. 函数的执行过程，并不依赖外部。
1. 修改、移除或者新增代码变得更为简单，能清晰地知道哪里能改哪里不能改。
1. 无论在哪里执行函数，只要输入的东西相同，得到的结果一定是一样的。

## 相关术语

- callbacks

    The functions that are slipped or passed into another function to decide the invocation of that function.

- first class

    Functions that can be assigned to a variable, passed into another function, or returned from another function just like any other normal value, are called `first class` functions. In JavaScript, all functions are `first class` functions.

- higher order

    The functions that take a function as an argument, or return a function as a return value are called `higher order` functions.

- lambda

    When the functions are passed in to another function or returned from another function, then those functions which gets passed in or returned can be called a `lambda`.

- mutation && side effect

    In functional programming, changing or altering things is called `mutation`, and the outcome is called a `side effect`.

- pure function

    A function, ideally, should be `a pure function`, meaning that it does not cause any side effects.

## 相关函数

freeCodeCamp 函数式编程这一部分是以数组来据例子的，所以大部分所涉及到的函数都是与数组相关。

例如：

 - map
 - filter
 - slice
 - concat
 - reduce
 - join
  - split：将字符串转换为数组
 - every
 - some

这个数组的处理函数都有一个特点，那就是使用它们的时候并不会改变原来的数组，而是生成一个新的数组。利用这些函数去处理数组，其实体现的就是函数式编程中“无副作用”的原则。

Functional Programming 这部分有很多体现“无副作用”的原则的练习，例如：

利用 `slice()` 删除元素，而不是利用 `shift()` 或者 `pop()`。

利用 `concat()` 来向数组中添加元素，而不是利用 `unshift()` 或者 `push()`。

使用 `sort()` 对数组进行排序之前，会先生成一个新的数组，`sort()` 是对新数组进行排序，而不是对原来的数组进行排序。

## Currying and Partial Application

### curring

The `arity` of a function is the number of arguments it requires. `Currying` a function means to convert a function of N `arity` into N functions of `arity` 1.

定义中很清晰地定义了柯里化的作用就是将有 N 个参数的函数，转换为 N 个仅有一个参数的函数。

练习中提到了柯里化的作用：

This is useful in your program if you can't supply all the arguments to a function at one time. You can save each function call into a variable, which will hold the returned function reference that takes the next argument when it's available.

```js
//Un-curried function
function unCurried(x, y) {
  return x + y;
}

//Curried function
function curried(x) {
  return function(y) {
    return x + y;
  }
}
curried(1)(2) // Returns 3
```

### partial application


partial application 的定义

`partial application` can be described as applying a few arguments to a function at a time and returning another function that is applied to more arguments.

从定义中可以看出 partial application (这个词不知道怎么翻译成中文，哈哈哈) 的主要作用就是，将一个含有多个参数的函数，加工处理成传递更少参数的函数。

```js
//Impartial function
function impartial(x, y, z) {
  return x + y + z;
}
var partialFn = impartial.bind(this, 1, 2);
partialFn(10); // Returns 13
```
