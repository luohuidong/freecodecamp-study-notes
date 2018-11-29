---
id: lookahead
title: Lookahead
---

There are two kinds of lookaheads: `positive lookahead` and `negative lookahead`.

## positive lookahead

FreeCodeCamp 中的定义：

A `positive lookahead` will look to make sure the element in the search pattern is there, but won't actually match it. A positive lookahead is used as `(?=...)` where the `...` is the required part that is not matched.

MDN 中的定义：

`x(?=y)`: Matches 'x' only if 'x' is followed by 'y'. This is called a **lookahead**.

For example, `/Jack(?=Sprat)/` matches 'Jack' only if it is followed by 'Sprat'. `/Jack(?=Sprat|Frost)/` matches 'Jack' only if it is followed by 'Sprat' or 'Frost'. However, neither 'Sprat' nor 'Frost' is part of the match results.

## nagative lookahead

FreeCodeCamp 中的定义：

A `negative lookahead` will look to make sure the element in the search pattern is not there. A negative lookahead is used as `(?!...)` where the ... is the pattern that you do not want to be there. The rest of the pattern is returned if the negative lookahead part is not present.

MDN 中的定义：

`x(?=y)`: Matches 'x' only if 'x' is not followed by 'y'. This is called a negated lookahead.

For example, `/\d+(?!\.)/` matches a number only if it is not followed by a decimal point. The regular expression `/\d+(?!\.)/.exec("3.141")` matches '141' but not '3.141'.

## use

FreeCodeCamp 对 lookahead 的作用的描述：

> This can be useful when you want to search for multiple patterns over the same string.

结合下面的例子就能理解这句话的意思了。

Here is a (naively) simple password checker that looks for between 3 and 6 characters and at least one number:

```js
let sayHi1 = 'Hi, Foo';
let sayHi2 = 'Hi, Bar';
let sayHi3 = 'Hi, Jack';

let regex = /Hi,\s(?!Foo)(?!Bar)/;

console.log(sayHi1.match(regex)); // Return null
console.log(sayHi2.match(regex)); // Return null
console.log(sayHi3.match(regex)); // Return [ 'Hi, ', index: 0, input: 'Hi, Jack' ]
```

有趣的地方在于，在匹配 `Foo`, `Bar`, `Jack` 这一部分的字符串 pattern 中可以定义多个 lookahead。也就是说，多个 lookahead 规则都作用于这部分的字符串。

## 参考资料

- [x(?=y)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#special-lookahead)
- [x(?!y)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions#special-negated-look-ahead)
- [Positive and Negative Lookahead](https://learn.freecodecamp.org/javascript-algorithms-and-data-structures/regular-expressions/positive-and-negative-lookahead)
