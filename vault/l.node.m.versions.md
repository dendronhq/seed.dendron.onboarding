---
id: d22865e3-1b00-4a83-96c6-b34de27732a4
title: Versions
desc: ''
updated: 1609368757363
created: 1609368714248
---



## 12

- https://stackoverflow.com/questions/59787574/typescript-tsconfig-settings-for-node-js-12
- As of Node.js 12.0.0, 100% of ES2019 is supported
- typescript
    - "target": "es2019"
    - "lib": ["es2019", "es2020.bigint", "es2020.string", "es2020.symbol.wellknown"]

```
{
  "compilerOptions": {
    "lib": ["es2019", "es2020.bigint", "es2020.string", "es2020.symbol.wellknown"],
    "module": "commonjs",
    "target": "es2019"
  }
}
```