---
id: f0289031-2962-4a4e-9ff7-3fa280fe06a2
title: Module-alias
desc: ''
updated: 1600971656304
created: 1600971656304

sources:
  - name: ""
    url: https://www.npmjs.com/package/module-alias
    license: ""
---

# Summary

Create aliases of directories and register custom module paths in NodeJS like a boss!

# Quickstart

```json
// Aliases
"_moduleAliases": {
  "@root"      : ".", // Application's root
  "@deep"      : "src/some/very/deep/directory/or/file",
  "@my_module" : "lib/some-file.js",
  "something"  : "src/foo", // Or without @. Actually, it could be any string
}
 
// Custom module directories, just like `node_modules` but with your private modules (optional)
"_moduleDirectories": ["node_modules_custom"],

require('module-alias/register')
```