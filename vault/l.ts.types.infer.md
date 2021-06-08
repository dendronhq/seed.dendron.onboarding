---
id: 13174c9c-62da-4da8-8a06-cb3ebacc31bd
title: Infer
desc: ''
updated: 1607612968111
created: 1607612912383
---

## Summary

infer helps unpack values

### eg1

```ts
type Unpromisify<T> = T extends Promise<infer R> ? R : T
```

* We check if type extends Promise
* If it does we extract the type from the promise
* If it does not leave it as is


## Related

## Sources:
- 'https://dev.to/aexol/typescript-tutorial-infer-keyword-2cn'