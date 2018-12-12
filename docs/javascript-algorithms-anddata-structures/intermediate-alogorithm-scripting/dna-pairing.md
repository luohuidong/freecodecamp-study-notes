---
id: dna-pairing
title: DNA Pairing
---

```js
const getPair = (char) => {
  switch (char) {
    case 'A':
      return 'T';
    case 'C':
      return 'G';
    case 'G':
      return 'C';
    case 'T':
      return 'A';
  }
}

function pairElement(str) {
  const strArr = [...str];
  const arr = strArr.map(element => [element, getPair(element)])
  return arr;
}

pairElement("GCG");
```
