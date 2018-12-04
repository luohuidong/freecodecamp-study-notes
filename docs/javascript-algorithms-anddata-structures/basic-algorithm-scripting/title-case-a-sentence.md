---
id: title-case-a-sentence
title: Title Case a Sentence
---

个人思路：

- 将字符串拆分为数组
- 将字符串的第一个字符转换为大写，其他字符转换为小写
- 将数组转换为字符串

```js
function titleCase(str) {
  let arr = str.split(' ').map(element => {
    if (element.length === 1) {
      return element[0].toUpperCase();
    } else {
      return element[0].toUpperCase() + element.slice(1).toLowerCase();
    }
  })
  return arr.join(' ');
}

titleCase("I'm a little tea pot");
```

FreeCodeCamp 中提供了三种思路：

初级思路：

- 先将字符串转换为数组。
- 将数组中的元素转换为小写，再将数组中的第一个字符转换为大写。
- 巧妙地利用了 String 的原型。

```js
String.prototype.replaceAt = function(index, character) {
    return this.substr(0, index) + character + this.substr(index+character.length);
};

function titleCase(str) {
    var newTitle = str.split(' ');
    var updatedTitle = [];
    for (var st in newTitle) {
        updatedTitle[st] = newTitle[st].toLowerCase().replaceAt(0, newTitle[st].charAt(0).toUpperCase());
    }
    return updatedTitle.join(' ');
}
```

初级思路中提供的代码，我变换以下，让代码更好理解。

```js
String.prototype.replaceFirstLetter = function () {
  const firstLetter = this[0].toUpperCase();
  return `${firstLetter}${this.substring(1)}`;
};

function titleCase(str) {
  const titleArray = str.split(' ');

  const updatedTitleArray = titleArray.map(element => {
    return element.toLowerCase().replaceFirstLetter();
  })

  return updatedTitleArray.join(' ');
}

const result = titleCase("I'm a little tea pot");
```

中级思路：

- 将字符串转换转换为小写，随后转换为数组。
- 利用 `replace()` 将字符串的第一个字符转换为大写，`replace()` 的作用可以查阅 [DevDocs replace](https://devdocs.io/javascript/global_objects/string/replace)

```js
function titleCase(str) {
  var convertToArray = str.toLowerCase().split(" ");

  var result = convertToArray.map(function(val){
      return val.replace(val.charAt(0), val.charAt(0).toUpperCase());
  });

  return result.join(" ");
}

titleCase("I'm a little tea pot");
```

高级思路：

- 比较巧妙地利用了正则表达式
- 利用 `replace()` 将字符串的第一个字符转换为大写，`replace()` 的作用可以查阅 [DevDocs replace](https://devdocs.io/javascript/global_objects/string/replace)

```js
function titleCase(str) {
  return str.toLowerCase().replace(/(^|\s)\S/g, (L) => L.toUpperCase());
}
```
