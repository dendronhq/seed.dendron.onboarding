---
id: e3ea65f5-fc92-4316-9a67-9b2852660b42
title: tmp
desc: ''
updated: 1596127989273
created: 1596127989273

links: |
  - https://www.npmjs.com/package/tmp
---

# Cook

### graceful cleanup

- clean everything on `process.exit`

```js
const tmp = require('tmp');
 
tmp.setGracefulCleanup();
```

### create directory sync

```js
const tmp = require('tmp');
 
const tmpobj = tmp.dirSync();
console.log('Dir: ', tmpobj.name);
/**
{
  name: '/var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-4449-Whh8THXsiqms',
  removeCallback: [Function: _cleanupCallback]
}
**/
// Manual cleanup
tmpobj.removeCallback();
```

### create unique filename sync
```js
const tmp = require('tmp');
 
const name = tmp.tmpNameSync();
console.log('Created temporary filename: ', name);
```
