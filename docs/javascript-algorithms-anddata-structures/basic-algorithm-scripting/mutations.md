---
id: mutations
title: Mutations
---

个人思路：

- 将数组中的元素都转换为小写，这样就解决了元素中包含大小写不方便判断的问题了。
- 遍历第二个元素当中的所有字符，判断是否存在与第一个元素当中。

```js
function mutation(arr) {
  const firstElement = arr[0].toLowerCase();
  const secondElement = arr[1].toLowerCase();

  for(let i = 0; i < secondElement.length; i++) {
    if (firstElement.indexOf(secondElement[i]) < 0) {
      return false;
    }
  }
  return true;
}

mutation(["hello", "hey"]);
```

我们来看看 FreeCodeCamp 提供的中级思路

```js
function mutation(arr) {
  return arr[1].toLowerCase()
    .split('')
    .every(function(letter) {
      return arr[0].toLowerCase()
        .indexOf(letter) != -1;
    });
}
```

我将中级思路中的代码，拆分了以下，方便理解。

思路依然是：

- 将数组元素转换为小写
- 判断第二个元素中的字符是否存在于第一个元素当中

```js
function mutation(arr) {
  const firstElement = arr[0].toLowerCase();
  const secondElementArray = arr[1].toLowerCase().split('');
  return secondElementArray.every(letter => firstElement.indexOf(letter) != -1)
}
```
