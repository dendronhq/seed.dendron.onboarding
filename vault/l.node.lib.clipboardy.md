---
id: 06000315-1d47-45be-9b2e-eaecb3ef9645
title: clipboardy
desc: ''
updated: 1595598366156
created: 1595598366156
stub: false
links: |
  - https://github.com/sindresorhus/clipboardy
---


# Usage
```js
const clipboardy = require('clipboardy');

clipboardy.writeSync('🦄');
clipboardy.writeSync('foo');

clipboardy.readSync();
//=> '🦄'

```
