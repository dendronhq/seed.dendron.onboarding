---
id: d277e8d1-1ce3-427b-9389-8b08722270c2
title: Typescript
desc: ''
updated: 1638927774279
created: 1593881250955

customLegacy:
  schema: lang
---
## Pin
- https://github.com/typescript-cheatsheets/react-typescript-cheatsheet

## ToC
- [[l.ts.d]]
- [[l.ts.d.modifiers]]
- [[l.ts.d.advanced]]
- [[l.ts.d.generics]]
- [[l.ts.ref.config]]
- [[l.ts.issues]]
- [[l.ts.object]]

## === Use


### runtime validation
- https://nodejs.libhunt.com/safen-alternatives

### ambient module

```ts
// In a .d.ts file or .ts file that is not a module:
declare module "SomeModule" {
  export function fn(): string;
}
```

- eg2
```ts
// firetruck.d.ts
declare function extinguish(theta: number,
                            phi: number,
                            pressure: number): Promise<void>;
export default extinguish;


```
### use union types as keys

```ts
type ComponentName = "TopBar"|"Foo";
const ALL_COMPONENTS: { [key in ComponentName]: ComponentProps } = {
  TopBar,
};
```

### make readonly prop mutable
link: https://stackoverflow.com/questions/46634876/how-can-i-change-a-readonly-property-in-typescript

```ts
type Mutable<U> = {
  -readonly [K in keyof U]: U[K];
};

```

## === Advanced

## Intersection

- usecase: only showing that some data should be optional

```ts
  static createContentNode(
    nodeProps: Omit<ContentNode, "data" | "logicalId"> &
      Partial<Pick<ContentNode, "logicalId">>,
    nodeData: Pick<ContentData, "title"> & Partial<ContentData>
  ): ContentNode {
```
