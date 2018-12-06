---
id: closure
title: Closure
---

Closure 的定义：

> In JavaScript, a function always has access to the context in which it was created. This is called closure.

Closure 也就是我们所说的闭包。

在 Use Closure to Protect Properties Within an Object from Being Modified Externally 这个练习中，介绍了如何利用 Closure 去实现对象的属性不被外部所修改。

一般在构造函数中，会像下面的例子那样去声明。实例化的对象的属性，能够在外部直接被修改。

```js
function People(name) {
  this.name = name;
  this.sayHi = function() {
    console.log(`My name is ${this.name}.`)
  }
}

const foo = new People('foo');
foo.sayHi(); // My name is foo.
foo.name = 'bar';
foo.sayHi(); // My name is bar.
```

如果希望实例化的对象的属性不被外部直接修改，可以像下面的例子将对象的属性声明为构造函数的内部属性。属性的获取和修改都只能通过构造函数中定义的接口去获取和修改。

```js
function People(initialName) {
  let name = initialName;
  this.sayHi = function() {
    console.log(`My name is ${name}.`);
  }
  this.setName = function(newName) {
    name = newName;
  }
}

const foo = new People('foo');
foo.sayHi(); // My name is foo.
foo.setName('bar');
foo.sayHi(); // My name is bar.
```

再回顾一下联系中，对 Closure 的定义：

> In JavaScript, a function always has access to the context in which it was created. This is called closure.

第二种构造函数的声明，就是巧妙地利用了闭包的特性，实现了对象不被外部直接修改的要求。

参考资料：

- [FreeCodeCamp: Use Closure to Protect Properties Within an Object from Being Modified Externally](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming/use-closure-to-protect-properties-within-an-object-from-being-modified-externally)
