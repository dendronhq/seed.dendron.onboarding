---
id: 34ab38a9-9875-4f1e-8fb2-1d44f83dd7b5
title: Issues
desc: ''
updated: 1612285972422
created: 1597895567220
stub: false
---

### Unparenthesized function
- source: https://stackoverflow.com/questions/50374908/transform-union-type-to-intersection-type

### 'this' implicitly has type 'any' because it does not have a type annotation


### This expression is not callable.

This expression is not callable.
  Each member of the union type '(<TResult = never>(onrejected?: ((reason: any) => TResult | PromiseLike<TResult>) | null | undefined) => Promise<string | Uri[] | TResult | undefined>) | (<TResult = never>(onrejected?: ((reason: any) => TResult | PromiseLike<...>) | ... 1 more ... | undefined) => Promise<...>)' has signatures, but none of those signatures are compatible with each other.ts(2349)


### The inferred type cannot be named without a reference to...
- issues: https://github.com/microsoft/TypeScript/issues/29808

```js
src/engineClient.ts:108:9 - error TS2742: The inferred type of 'deleteNote' cannot be named without a reference to '@dendronhq/common-server/node_modules/@dendronhq/common-all'. This is likely not portable. A type annotation is necessary.

```

### An index signature parameter type cannot be a union type. Consider using a mapped object type instead.
- link: https://github.com/microsoft/TypeScript/issues/24220

- fix
```ts
type Foo = 'a' | 'b';
type Bar = {[key in Foo]: any};
```

# --- Rest
# New

### Cannot find module 'fast-csv'.
- need to declare module

# Bucket
## Type Promise<{}> is not asisgnable to type Promise<void>
- url: https://github.com/Microsoft/TypeScript/issues/8516

- issue: passing in empty resolve will result in typescript type error

## Import module without ts.d file #index
- https://github.com/Microsoft/TypeScript/issues/3019

## TS1005: '>' expected

## Error TS1128: Declaration or statement expected.

##  TS1183: An implementation cannot be declared in ambient contexts

##  Error TS2304: Cannot find name 'require'

## TS2307: Cannot find module 'backbone'

## TS2339: Property 'type' does not exist on type
- react

## TS2403: Subsequent variable declarations must have the same type.

## TS2503: Cannot find namespace 'NodeJS'

## TS2664: Invalid module name in augmentation, module

##  TS4026: '' of exported class has or is using name '' ... but cannot be named
- error TS4026: Public static property 'meta' of exported class has or is using name 'Encounter' from external module "/Users/linkevi/workplace/curator_node/src/Curator_widget_rx_price/node_modules/edison-base/lib/src/models/encounter" but cannot be named.
- https://github.com/Microsoft/TypeScript/issues/5711


### Duplicate Identifier with tsc 2.8.3
- https://github.com/Microsoft/TypeScript/issues/23755

### ... because it would overwrite input file
url: https://stackoverflow.com/questions/42609768/typescript-error-cannot-write-file-because-it-would-overwrite-input-file

- need to exclude the `outDir` in the `exclude` category

# --- The expected type comes from property 'sample_rate' which is declared here on type 'startTranscriptionOpts'
id: ED5CABC7-6B29-45F1-9261-EE9D37A5C3C9
created: 2019-02-02T10:02
pro:
status:
tags: []



# --- how-to-get-optional-chaining-working-in-typescript
id: 113F54ED-B7CB-42F1-98B0-4755D6168A8D
created: 2020-02-08T10:15
tags: []
category: []

- source: https://stackoverflow.com/questions/58725711/how-to-get-optional-chaining-working-in-typescript
