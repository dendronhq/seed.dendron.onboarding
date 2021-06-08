---
id: 6e85e973-3fe9-4cfe-80db-d282d2f85de1
title: D
desc: ''
updated: 1597895566591
created: 1597895566591
stub: false
---

# Mapped

```ts
type Readonly<T> = {
    readonly [P in keyof T]: T[P];
}
type Partial<T> = {
    [P in keyof T]?: T[P];
}

```


# Conditional
links: 
- https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-8.html

## restrictions
- conditional types cannot refer to themselves recursively
```ts
type Tree<T> = T extends any ? Tree<T>
```

## gen
- selects one of two possible types based on condition expressed as a type relationship test

```
T extends U ? X: Y
```

- deferred conditional types
    - instead of picking branch, passing in generics to a func with conditional type means the type won't be evaluated until the wrapper function is called

```ts
declare function f<T>(x: T): T extends Foo ? string: number

function foo<U>(x: U) {
    // this type is not evaluated yet
    let a = f(x)
    // assignment needs to assume either type
    let b: string|number = a
}
```

- distributive conditional types
    - if checked type is a naked type parameter, then type is distributed over union types
    ```ts
    T extends U ? X : Y where T = A|B|C
    then
    (A extends U ? X: Y) | (B extends U ? X: Y) | ...
    ```
    - these can be used to make filters
    ```ts
    // only get properties that are not in T
    type Diff = T extends U ? never : T
    // only get properties that are in T
    type Filter = T extends U ? T : never
    ```
- combine with mapped types
```ts
// only get properties that extend Function
type FunctionPropertyNames<T> = { [K in keyof T]: T extends Function ? K : never }
```

- advanced
```ts
type ReturnType<T> = T extends (...args: any[]) => infer R ? R : any;
```

- pre-defined
```ts
- Exclude<T, U> // Exclude from T those types that are assignable to U.
- Extract<T, U> // Extract from T those types that are assignable to U.
- NonNullable<T> // Exclude null and undefined from T.
- ReturnType<T> // Obtain the return type of a function type.
- InstanceType<T> // Obtain the instance type of a constructor function type
```
