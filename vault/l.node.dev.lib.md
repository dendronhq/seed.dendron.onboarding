---
id: 53ef7dd4-22e0-4193-88e2-f54b51f3d9e9
title: Lib
desc: ''
updated: 1608403204728
created: 1598636320508

---

## --- Dep Resolution
- http://fredkschott.com/post/2014/06/require-and-the-module-system/
- https://lexi-lambda.github.io/blog/2016/08/24/understanding-the-npm-dependency-model/

## Details
- each package can have its own dependency tree

## Topics

### peerDependencies
- expect this dependency to be satisfied by its dependent package
- use this if module exports or depends on modules from other packages

- export
```
import {Bar} from "bar";

// need a peer dependency
export const createBar = () => (new Bar())

```

- require
```
import {Bar} from "bar"

export const consumeBar = (bar: Bar) => { ... }

```

- example
```json
{
  "name": "chai-as-promised",
  "peerDependencies": {
    "chai": "1.x"
  }
}
```

## === Rest


## === External
- [[node.lib-cheerio]]: lean implementation of jQuery for server

## DB
- [[node.lib-mysql]]

## QA
- [[node.lib-gulp.read]]

## Topics

### Installation
- res: https://stackoverflow.com/questions/5926672/where-does-npm-install-packages

- globals
    - /usr/local/lib/node
    - /usr/local/lib/node_modules

- locals
    - $cwd/node_modules
