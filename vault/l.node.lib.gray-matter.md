---
id: 123cd0fe-72fb-460c-9419-02edf8e6aff8
title: r.node.lib-gray_matter
desc: ''
updated: 1603138990543
created: 1598195815392

links: |
  - https://www.npmjs.com/package/gray-matter
---
# Quickstart

```bash
$ npm install --save gray-matter

```


```js
console.log(matter('---\ntitle: Front Matter\n---\nThis is content.'));

// return
file.data {Object}: the object created by parsing front-matter
file.content {String}: the input string, with matter stripped
file.excerpt {String}: an excerpt, if defined on the options
file.empty {String}: when the front-matter is "empty" (either all whitespace, nothing at all, or just comments and no data), the original string is set on this property. See #65 for details regarding use case.
file.isEmpty {Boolean}: true if front-matter is empty.
```

- stringify
```js
console.log(matter.stringify('foo bar baz', {title: 'Home'}));
// results in:
// ---
// title: Home
// ---
// foo bar baz

```

can you submit a feature request so we can track it in our roadmap? https://github.com/dendronhq/dendron/issues/new?assignees=&labels=&template=feature_request.md&title=

# API

  * file.orig {Buffer}: the original input string (or buffer)
  * file.language {String}: the front-matter language that was parsed. yaml is the default
  * file.matter {String}: the raw, un-parsed front-matter string
  * file.stringify {Function}: stringify the file by converting file.data to a string in the given language, wrapping it in delimiters and prepending it to file.content.
