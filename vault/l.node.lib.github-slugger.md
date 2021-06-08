---
id: d943de54-b407-49cd-9f65-d671674791a8
title: Github-slugger
desc: ''
updated: 1600015872428
created: 1600015872428
stub: false
source: |
  - https://github.com/Flet/github-slugger
---

# Quickstart

```
npm install github-slugger
```

```ts
var GithubSlugger = require('github-slugger')
var slugger = new GithubSlugger()

slugger.slug('foo')
// returns 'foo'

slugger.slug('foo')
// returns 'foo-1'

slugger.slug('bar')
// returns 'bar'

slugger.slug('foo')
// returns 'foo-2'

slugger.reset()

slugger.slug('foo')
// returns 'foo'
```
