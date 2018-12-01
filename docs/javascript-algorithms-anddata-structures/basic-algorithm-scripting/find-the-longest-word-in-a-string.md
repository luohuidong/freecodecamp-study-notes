---
id: find-the-longest-word-in-a-string
title: Find the Longest Word in a String
---

个人解题思路：

- 将字符串转换为数组
- 用 `sort()` 对数组进行排序
- 输出最长字符串的长度

```js
function findLongestWordLength(str) {
  const arr = str.split(' ');
  const sortedArr = arr.sort((a, b) => a.length - b.length)
  return sortedArr[sortedArr.length - 1].length;
}

findLongestWordLength("The quick brown fox jumped over the lazy dog");
```

freeCodeCamp 给出了三种解题思路，这三种思路都是围绕了以下几点来解题：

- 获取每个字符串的长度
- 对比每个字符串的长度
- 保存最长的字符串长度


最为基础的思路：

- 将字符串转换为数组
- 定义一个变量 `maxLength`，保存最长的字符串长度。（保存最长的字符串长度）
- 遍历数组，将该轮循环中的字符串长度与 `maxLength` 的大小进行比较，如果比 `maxLength` 大，则该轮循环的字符串长度赋值给 `maxLength`。（获取每个字符串长度，对比每个字符串的长度）

```js
function findLongestWordLength(str) {
  var words = str.split(' ');
  var maxLength = 0;

  for (var i = 0; i < words.length; i++) {
    if (words[i].length > maxLength) {
      maxLength = words[i].length;
    }
  }

  return maxLength;
}
```

中级解题思路：

- 将字符串转换为数组
- 利用 `reduce` 保存最长字符串长度。（保存最长字符串长度）
- 利用 `Math.max()` 获取最长字符串长度。（获取每个字符串长度，获取最长字符串长度）

```js
function findLongestWordLength(s) {
  return s.split(' ').reduce((x, y) => Math.max(x, y.length), 0);
}
```

高级解题思路（非常有意思的思路，但说实话，我个人比较喜欢中级解题思路，因为简洁易懂）：

- 将字符串转换为数组。
- 运用递归。
- 数组最终仅保留最长长度的字符串。

```js
function findLongestWordLength(str) {

  //split the string into individual words
  //(important!!, you'll see why later)
  str = str.split(" ");

  //str only has 1 element left that is the longest element,
  //return the length of that element
  if(str.length == 1){
    return str[0].length;
  }

  //if the first element's length is greater than the second element's (or equal)
  //remove the second element and recursively call the function)
  if(str[0].length >= str[1].length){
    str.splice(1,1);
    return findLongestWordLength(str.join(" "));
  }

  //if the second element's length is greater thant the first element's start
  //call the function past the first element
  if(str[0].length <= str[1].length){
    // from the first element to the last element inclusive.
    return findLongestWordLength(str.slice(1,str.length).join(" "));
  }
}
```
