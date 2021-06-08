---
id: 1815c2bd-e748-4f03-8ed5-b4b9e26b4048
title: Advanced
desc: ''
updated: 1609611738210
created: 1597895568360
stub: false
---

### Parameters

Get type parameters

```ts
type TestParams = Parameters<(a: string, b: number) => void> // [string, number]

```

https://stackoverflow.com/questions/51851677/how-to-get-argument-types-from-function-in-typescript


### merging interfaces
```ts

// the below 
interface Document {
    createElement(tagName: any): Element;
}
interface Document {
    createElement(tagName: "div"): HTMLDivElement;
    createElement(tagName: "span"): HTMLSpanElement;
}
interface Document {
    createElement(tagName: string): HTMLElement;
    createElement(tagName: "canvas"): HTMLCanvasElement;
}

// becomes
interface Document {
    createElement(tagName: "canvas"): HTMLCanvasElement;
    createElement(tagName: "div"): HTMLDivElement;
    createElement(tagName: "span"): HTMLSpanElement;
    createElement(tagName: string): HTMLElement;
    createElement(tagName: any): Element;
}
```

### merging namespaces

```ts
namespace Animals {
    export class Zebra { }
}

namespace Animals {
    export interface Legged { numberOfLegs: number; }
    export class Dog { }
}
```

### module augmentation
link: https://github.com/Microsoft/TypeScript-Handbook/blob/fa9e2be1024014fe923d44b1b69d315e8347e444/pages/Declaration%20Merging.md#module-augmentation

```ts
// observable.ts stays the same
// map.ts
import { Observable } from "./observable";
declare module "./observable" {
    interface Observable<T> {
        map<U>(f: (x: T) => U): Observable<U>;
    }
}
Observable.prototype.map = function (f) {
    // ... another exercise for the reader
}

// consumer.ts
import { Observable } from "./observable";
import "./map";
let o: Observable<number>;
o.map(x => x.toFixed());
```

- augment global module
```ts
// observable.ts
export class Observable<T> {
    // ... still no implementation ...
}

declare global {
    interface Array<T> {
        toObservable(): Observable<T>;
    }
}

Array.prototype.toObservable = function () {
    // ...
}
```

- short exapmle

```ts
declare module "slugify" {
  function out(arg1: any, arg2: any): string
  export = out
}

```
