---
id: ddb4cb9e-24cb-4288-9bbb-8eb6f9f7e5e1
title: Fs-extra
desc: ''
updated: 1604100866774
created: 1598636365013

---

## fs-extra
- https://github.com/jprichardson/node-fs-extra#copy

# === Issues

### Namespace '"fs"' has no exported member 'Dir'.
link: https://github.com/DefinitelyTyped/DefinitelyTyped/issues/44946
res: update @types/node

```ts
node_modules/@types/fs-extra/index.d.ts:188:87 - error TS2694: Namespace '"fs"' has no exported member 'Dir'.

188 export function opendir(path: string, cb: (err: NodeJS.ErrnoException | null, dir: fs.Dir) => void): void;
```

# === API

### copy
link: https://github.com/jprichardson/node-fs-extra/blob/master/docs/copy.md
desc: Copy a file or directory. The directory can have contents.

- params:
  - src <String> Note that if src is a directory it will copy everything inside of this directory, not the entire directory itself (see issue #537).
  - dest <String> Note that if src is a file, dest cannot be a directory 
  - filter <Function>: Function to filter copied files. Return true to include, false to exclude. Can also return a Promise that resolves to true or false (or pass in an async function).


- with filter
  - gotcha: full path to file
  - return true to accept, false to reject

```
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/root.schema.yml /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/root.schema.yml

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/root.md /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/root.md

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/foo.schema.yml /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/foo.schema.yml

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/foo.md /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/foo.md

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/foo.ch1.md /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/foo.ch1.md

  console.log src/builtin/SnapshotPod.ts:55
    /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/vault/assets /var/folders/65/c9lrx0tx6k7b_zlb4v1bs2rr0000gn/T/tmp-84258-S5RhvF3k2C8p/snapshot/1604100350724/vault/assets

```

```js
const fs = require('fs-extra')

const filterFunc = (src, dest) => {
  // your logic here
  // it will be copied if return true
}

fs.copy('/tmp/mydir', '/tmp/mynewdir', { filter: filterFunc }, err => {
  if (err) return console.error(err)
  console.log('success!')
})
```


### readJSON

```
fs.readJson('./package.json', function (err, packageObj) {
  console.log(packageObj.version) // => 0.1.3
})
```

### readJsonSync(file, [options])


## Mutate

### fs.removeSync('/tmp/myfile')
- remove file or directory
- will work like rm -rf


### writeJsonSync(file, object, [options])
