---
id: binary-agents
title: Binary Agents
---

个人思路：

- 将二进制转换为十进制
- 利用 `fromCharCode` 将十进制转换为字符

```js
function binaryAgent(str) {
    const arr = str.split(' ')

    const newStr = arr
        .map(element => {
            const decimal = Number.parseInt(element, 2)
            return String.fromCharCode(decimal)
        })
        .join('')

    return newStr;
}

const result = binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
```
