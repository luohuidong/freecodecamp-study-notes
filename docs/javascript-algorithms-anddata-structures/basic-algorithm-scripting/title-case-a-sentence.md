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
