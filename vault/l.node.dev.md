---
id: 4c535cca-9089-4654-b207-b19613bf5070
title: r.node.dev
desc: ''
updated: 1609216941540
created: 1
stub: false
customLegacy:
  path: r.node.dev
---


# Tests
```json
"test": "cross-env NODE_ENV=test BABEL_DISABLE_CACHE=1 jest ",
"test:setup": "cross-env NODE_ENV=test BABEL_DISABLE_CACHE=1 ts-node --log-error ./app/scripts/setupTests.ts",
"test:unit:debug": "cross-env NODE_ENV=test BABEL_DISABLE_CACHE=1 node --inspect-brk node_modules/.bin/jest --runInBand",
"test:unit:debug": "NODE_ENV=test  node --inspect-brk node_modules/.bin/jest --runInBand",
"test:all": "yarn lint && yarn ts && yarn build && yarn test && yarn build-e2e && yarn test-e2e",
"test:e2e": "node -r @babel/register ./internals/scripts/CheckBuildsExist.js && cross-env NODE_ENV=test testcafe electron:./app ./test/e2e/HomePage.e2e.ts",
"test:e2e:live": "node -r @babel/register ./internals/scripts/CheckBuildsExist.js && cross-env NODE_ENV=test testcafe --live electron:./app ./test/e2e/HomePage.e2e.ts",
"test:watch": "yarn test --watch"

```
