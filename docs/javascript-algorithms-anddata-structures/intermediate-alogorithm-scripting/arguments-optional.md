---
id: arguments-optional
title: Arguments Optional
---

```js
const oneArgument = (a) => {
    return b => {
        const isNumber = typeof b === 'number'

        if (!isNumber) {
            return
        }

        return a + b
    }
}

function addTogether(...args) {
    const isNumber = args.every(element => typeof element === 'number')

    if (!isNumber) {
        return
    }

    if (args.length === 2) {
        return args.reduce((a, b) => a + b)
    } else {
        return oneArgument(args[0])
    }
}

addTogether(2,3);
```
