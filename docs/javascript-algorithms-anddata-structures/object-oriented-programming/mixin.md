---
id: mixin
title: Mixin
---

相关的对象的相同行为可以通过继承获取，但是如果不相关的对象也通过继承去获取相同的行为就有些不妥了。此时可以通过 mixin 方式，让两个不相关的对象，获取同样的行为。

```js
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};

let bird = {
  name: "Donald",
  numLegs: 2
};

let plane = {
  model: "777",
  numPassengers: 524
};

flyMixin(bird);
flyMixin(plane);
```

上面的例子中，鸟和飞机这两个不相关的对象，通过 mixin 的方式获取了相同的 fly 的行为。

参考资料：

- [FreeCodeCamp: Use a Mixin to Add Common Behavior Between Unrelated Objects](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/object-oriented-programming/use-a-mixin-to-add-common-behavior-between-unrelated-objects)
