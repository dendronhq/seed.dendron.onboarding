---
id: 8803fa4a-be55-473c-b808-e5bc3c149ba4
title: Glob
desc: ''
updated: 1599502983096
created: 1599502983096

published: true
source: |
  - https://www.npmjs.com/package/glob
---

## Summary

## Gotchas

## Synopsis

## Options

## Cook

```js
var glob = require("glob")
 
// options is optional
glob("**/*.js", options, function (er, files) {
  // files is an array of filenames.
  // If the `nonull` option is set, and nothing
  // was found, then files is ["**/*.js"]
  // er is an error object or null.
})
```
