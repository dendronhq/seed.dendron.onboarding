---
id: 3f9e3bb5-227e-47fe-a33a-e73978dabbc8
title: r.node.system
desc: ''
updated: 1
created: 1

customLegacy:
  path: r.node.system
---

# Env

## dirname

```
__dirname
```

## filename

```
__filename

```

## pathname
```

```

## read/write

```

```

# File
## operations

### exists

```
fs.existsSync(path: str): bool

```

# Cli

## Links
- https://nodejs.libhunt.com/inquirer-js-alternatives
- https://github.com/SBoudrias/Inquirer.js

- cli tables: https://github.com/cli-table/cli-table3
  - ![](assets/2020-06-05-06-46-33.png)

## Argv
process.argv

# UUID
- Tiny, secure, URL-friendly, unique string ID generator: https://nodejs.libhunt.com/nanoid-alternatives

# Etc

## sleep

- native
```bash
function msleep(n) {
  Atomics.wait(new Int32Array(new SharedArrayBuffer(4)), 0, 0, n);
}
```

- https://www.npmjs.com/package/sleep

```bash
const sleep = require("sleep");
sleep.sleep(n) // n seconds
```
