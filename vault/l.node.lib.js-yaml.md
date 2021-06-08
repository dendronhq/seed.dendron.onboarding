---
id: b723bdcd-26f0-4397-bd7d-e378a66e4300
title: r.node.lib.js_yaml
desc: ''
updated: 1
created: 1
stub: false
customLegacy:
  path: r.node.lib.js_yaml
---

# Res
- https://github.com/nodeca/js-yaml

# Details
- turn json into yaml

# Dev Quickstart

```js
yaml = require('js-yaml');
fs   = require('fs');

// Get document, or throw exception on error
try {
  var doc = yaml.safeLoad(fs.readFileSync('/home/ixti/example.yml', 'utf8'));
  console.log(doc);
} catch (e) {
  console.log(e);
}

```

# API

### safeLoad

- options
  - schema
  - json


### safeDump

#### options
- indent (default: 2) - indentation width to use (in spaces).
- flowLevel (default: -1) - specifies level of nesting, when to switch from block to flow style for collections. -1 means block style everwhere
- schema (default: DEFAULT_SAFE_SCHEMA) specifies a schema to use.
- sortKeys (default: false) - if true, sort keys when dumping YAML. If a function, use the function to sort the keys.
- lineWidth (default: 80) - set max line width.
- noCompatMode (default: false) - if true don't try to be compatible with older yaml versions. Currently: don't quote "yes", "no" and so on, as required for YAML 1.1
- condenseFlow (default: false) - if true flow sequences will be condensed, omitting the space between a, b. Eg. '[a,b]', and omitting the space between key: value and quoting the key. Eg. '{"a":b}' Can be useful when using yaml for pretty URL query params as spaces are %-encoded.