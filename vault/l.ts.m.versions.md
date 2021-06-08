---
id: 9feeaece-5206-4d4d-9d3e-042de1797740
title: Versions
desc: ''
updated: 1608769975148
created: 1593881250956
stub: false
---

# 3.9
src: https://devblogs.microsoft.com/typescript/announcing-typescript-3-9/

### features
- faster compilation times

### ts-expect-error

```ts
function doStuff(abc: string, xyz: string) {}

expect(() => {
    doStuff(123, 456);
}).toThrow();

// us @ts-expect-error in thi situation
    doStuff(123, 456);
//          ~~~
// error: Type 'number' is not assignable to type 'string'.

```

# 3.7
- has ?. operator

# 3.5

- - id: 8753B4BB-BC3B-416A-82AD-9F4704F85EA8
  title: 3.5
  created: 2019-06-02T21:49:00.000Z
  tags: []
  url: https://devblogs.microsoft.com/typescript/announcing-typescript-3-5/
  data: |
    - much faster type checking and incremental compilation
    - faster `--incremental` builds
    - `Omit` helper
    - better checking on excesss properties in union
    - `allowUmdGlobalAccess` flag, work with old style javascript modules
    - smarter union type checking
    - better generics
    - editor
        - smart select in editor, don't just rely on brace expansion
        - extract inline types to type alias

- id: 6CEDDF96-2DAB-4C44-B6A4-E0438D1FB28C
  title: 2.8
  created: 2018-04-29T18:28:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2018/03/27/announcing-typescript-2-8/
  data: |
    - features:
        - conditional types: help with generics
        - declaration-only emit flag: compile step, only emit declaration files
        - @jsx pragma comments: allow diff jsx factory on per file basis
        - JSX resolve based on factory: help allow diff jsx factory
        - mapped types operations: use `+` to add modifiers and `-` to remove modifeirs
        - lang service can org imports
        - lang service initialize uninitialized properties
    - breaking:

- id: E78CDD1A-1D74-4C38-81DE-2F9AD83ABD08
  title: 2.0
  created: 2018-04-29T18:38:00.000Z
  tags: []
  data: |
    - features
        - non-nullable types
        - easy module declaration
            ```
            // old
            declare module "foo" {
                var x: any;
                export = x;
            }

            declare module "foo";
            ```
        - more literal types: boolean, number, enum
        - globs in tsconfig

- id: 5BBF48C3-36F9-4CD5-AF49-F585C1A7AA5B
  title: 2.1
  created: 2018-04-29T18:39:00.000Z
  tags: []
  data: |
    - features:
        - async function
        - object rest and spread: {...orig}
        - keyof and Lookup types

- id: FD621386-46F7-4E6C-8492-8089400F0346
  title: 2.2
  created: 2018-04-29T18:41:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2017/02/22/announcing-typescript-2-2/
  data: |
    - features:
        - object type: matches anythig except primitives
        - better string indexing: foo[key] and foo.key are both valid with following signature
            ```
            interface Foo {
                [prop: string]: bool
            }
            ```
        - class support for mixin: TODO
        - emit jsx like react does
        - use `new.target` feature in es: TODO

- id: B6C083A2-96E8-4CDF-90CF-AF59F40ADB71
  title: 2.3
  created: 2018-04-29T18:46:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2017/04/27/announcing-typescript-2-3/
  data: |
    - features:
        - typechecking in js files
        - lang server plugin
        - default types
            - eg: class Component<P, S = object>
        - compile generator and iterator

- id: 9D6CB9CD-7633-4956-93C4-336B59645A8F
  title: 2.4
  created: 2018-04-29T18:50:00.000Z
  res: https://blogs.msdn.microsoft.com/typescript/2017/06/27/announcing-typescript-2-4/
  tags: []
  data: |
    - features:
        - dynamic import: requires es2018 target
        - string enums
        - better generic checks

- id: 3634A7E5-CD49-486E-AC6B-12866669C1E6
  title: 2.5
  created: 2018-04-29T18:54:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2017/08/31/announcing-typescript-2-5/
  data: |
    - features:
        - optional catch
        - deduplicate imports packages with same name and version
        - --preserveSymlinks flag

- id: C9D6C36D-D81D-46C7-80D4-ED43BE7720E3
  title: 2.6
  created: 2018-04-29T18:57:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2017/10/31/announcing-typescript-2-6/
  data: |
    - features:
        - faster --watch mode
        - more type checks

- id: F967EDEE-8122-4D4B-9CCB-5C250BF7091B
  title: 2.7
  created: 2018-04-29T18:59:00.000Z
  tags: []
  res: https://blogs.msdn.microsoft.com/typescript/2018/01/31/announcing-typescript-2-7/
  data: |
    - features:
        - synthetic import
        - strict class check
        - definite assignment assertion: tell typescript value will be assigned
            ```
            let x!: number[];
            initialize();
            x.push(4);

            ```



# --- Old
# 1.0

## 1.1
- 4x faster

## 1.8.10
- latest: true
    - checked: 2016-06-28

- features
    - f-bounded polymorphism
        - possible for type parameter constraint to reference type parameters from same type parameter list
        - https://www.typescriptlang.org/docs/release-notes/typescript-1.8.html
    - ability to augment global scope
    - string literal types
        - like symbol like strings
        eg:

            // string can only have these values
            intetrface Foo {
                easing: "ease-in" | "ease-out" | "ease-in-out";
            }
    - allowJS option
        - use `.js`  files with tsc
    - tsconfig now takes comments


# 2.0
- https://blogs.msdn.microsoft.com/typescript/2016/07/11/announcing-typescript-2-0-beta/

## Features
- https://blogs.msdn.microsoft.com/typescript/2016/08/30/announcing-typescript-2-0-rc/ , 2016-09-04

- non-nullable types
- control flow analysis for types
    - can figure out if types change after going through control flow constructs
- easy module declaration
- no async/await for ES3/ES5 targets yet

### Tagged Unions
- unions with same field but different literal types

### Globs in tsconfig

# 2.1
- https://blogs.msdn.microsoft.com/typescript/2016/12/07/announcing-typescript-2-1/

## Features

### async function

### object rest and spread

```
let copy = { ...orig };

```

### keyof and Lookup Types

- `keyof` is like "index type query"
    - `typeof` used as query of type values
    - `keyof` used as query of index names

```
interface Entity {
    name: string
    date: string
}

let entProp: keyof Entity;

// this is the same as

let entProp: name|date

```

- `[x]` is like "index access type" or "lookup type"
    - used as query of index value

```

let datePropValue: Entity["date"]

```


