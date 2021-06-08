---
id: 3005e40c-8ad8-48dc-bbb7-b2e589f030de
title: r.node.lib-klaw
desc: ''
updated: 1609133520969
created: 1594835872458
stub: false

---

## API

### klaw(directory, [options])
- Every read() or data event returns an object with two properties: `path` and `stats`. path is the full path of the file and stats is an instance of fs.Stats.
- params
    - directory: The directory to recursively walk. Type string
    - options
        - filter: (function, default: undefined): Filtering function for Arrays
        - depthLimit: (number, default: undefined): The number of times to recurse before stopping. -1 for unlimited.

## Quickstart
- https://github.com/jprichardson/node-klaw

```ts
const klaw = require('klaw')

const items = [] // files, directories, symlinks, etc
klaw('/some/dir')
  .on('readable', function () {
    let item
    while ((item = this.read())) {
      items.push(item.path)
    }
  })
  .on('end', () => console.dir(items)) // => [ ... array of files]

```

## Cook

### skipping directories

```js
const klaw = require('klaw')
const through2 = require('through2')

const excludeDirFilter = through2.obj(function (item, enc, next) {

  if (!item.stats.isDirectory()) this.push(item)
  next()
})

const items = [] // files, directories, symlinks, etc
klaw('/some/dir')
  .pipe(excludeDirFilter)
  .on('data', item => items.push(item.path))
  .on('end', () => console.dir(items)) // => [ ... array of files without directories]
```

### ignore hidden

```js
const klaw = require('klaw')
const path = require('path')

const filterFunc = item => {
  const basename = path.basename(item)
  return basename === '.' || basename[0] !== '.'
}

klaw('/some/dir', { filter: filterFunc })
  .on('data', item => {
    // only items of none hidden folders will reach here
  })
```
