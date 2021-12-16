---
id: 772fddf0-d73e-41cf-98f1-1ca8ee57f887
title: Unions
desc: ''
updated: 1611703884736
created: 1606246160672
---


- https://basarat.gitbook.io/typescript/type-system/discriminated-unions

```
interface Square {
    kind: "square";
    size: number;
}

interface Rectangle {
    kind: "rectangle";
    width: number;
    height: number;
}
type Shape = Square | Rectangle;
```

With functions
```ts
type FunctionUnion = (() => void) | ((p: string) => void);
```