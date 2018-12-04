---
id: chunky-monkey
title: Chunky Monkey
---

个人思路：

将数组按照传入的 `size` 进行分组，就可以利用 `splice()` 的特性，去删除数组中前两个元素，并获取删除了的元素（一开始有想过用 `pop()`，但是由于一次只能获取一个元素，感觉有点不方便就弃用了）。由于 `splice()` 是会改变原来的数组的，所以可以通过判断原来的数组长度是否为 0 来判断数组元素是否已经分组完毕。

当前这个还可以用 `slice()` 来进行处理，不过因为 `slice()` 处理之后是返回一个新的数组而不是改变原来的数组，因此判断条件需要调整。

```js
function chunkArrayInGroups(arr, size) {
  let newArray = []
  while(arr.length !== 0) {
    newArray.push(arr.splice(0, size));
  }
  return newArray;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```

FreeCodeCamp 提供了三种高级思路，前两种跟我的思路差不多，最后一种比较有意思，用到了递归，我们来看一下使用递归的思路。

- 通过 `slice()` 进行分组
- 每次递归，都是返回一个二维数组
- 利用 `concat()` 进行二维数组的合并

```js
function chunkArrayInGroups(arr, size) {
  if (arr.length <= size){
    return [arr];
  }
  else {
    return [arr.slice(0,size)].concat(chunkArrayInGroups(arr.slice(size),size));
  }
}
```
