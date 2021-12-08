---
id: 94ec02c5-2a8e-4a51-9691-84db733ebb65
title: Comment-json
desc: ''
updated: 1597073671954
created: 1597073671954

links: |
  - https://github.com/kaelzhang/node-comment-json
---


# Quickstart

```js
const {
  parse,
  stringify,
  assign
} = require('comment-json')
const fs = require('fs')

const obj = parse(fs.readFileSync('package.json').toString())

console.log(obj.name) // comment-json

stringify(obj, null, 2)
```
