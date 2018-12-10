---
id: wherefore-art-thou
title: Wherefor Art Thou
---

个人思路：

- 利用 filter 筛选数据
- 利用 for...in 循环获取第二个参数的每个属性，并且与第一个参数中的对象进行比较

```js
function whatIsInAName(collection, source) {
  // What's in a name?
  var arr = [];
  // Only change code below this line
  arr = collection.filter(collectionElement => {
    for (let key in source) {
      if (source[key] !== collectionElement[key]) {
        return false
      }
    }
    return true
  });

  // Only change code above this line
  return arr;
}

whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```

freeCodeCamp 提供的中级思路中使用了 `Object.key()` 获取第二个参数的 keys，并且利用 `every()` 来决定 `filter()` 返回值。

```js
function whatIsInAName(collection, source) {
  var srcKeys = Object.keys(source);

  return collection.filter(function (obj) {
    return srcKeys.every(function (key) {
      return obj.hasOwnProperty(key) && obj[key] === source[key];
    });
  });
}

whatIsInAName([{ first: "Romeo", last: "Montague" }, { first: "Mercutio", last: null }, { first: "Tybalt", last: "Capulet" }], { last: "Capulet" });
```
