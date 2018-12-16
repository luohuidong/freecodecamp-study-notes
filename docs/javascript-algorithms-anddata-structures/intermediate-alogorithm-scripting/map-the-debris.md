---
id: map-the-debris
title: Map the Debris
---

这道题比较简单，就是高中的物理知识，用了万有引力公式和圆周运动的公式。

```js
const getOrbitalPeriod = (altitude) => {
    var GM = 398600.4418;
    var earthRadius = 6367.4447;

    var r = altitude + earthRadius;

    let period = 2 * Math.PI * Math.sqrt(Math.pow(r, 3) / GM);
    period = period.toFixed(0);
    period = parseInt(period);
    return period
}

function orbitalPeriod(arr) {
    return arr.map(element => ({
        name: element.name,
        orbitalPeriod: getOrbitalPeriod(element.avgAlt),
    }));
}
```
