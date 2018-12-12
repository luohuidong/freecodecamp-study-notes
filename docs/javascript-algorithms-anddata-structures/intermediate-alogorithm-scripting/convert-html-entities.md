---
id: convert-html-entities
title: Convert HTML Entities
---

```js
function convertHTML(str) {
  let entities = {
    '&': '&amp;',
    '<': '&lt;',
    '>': '&gt;',
    '"': '&quot;',
    "'": '&apos;',
  }

  return str.replace(/([&<>"'])/g, match => {
    return entities[match]
  })
}

convertHTML("Dolce & Gabbana");
```
