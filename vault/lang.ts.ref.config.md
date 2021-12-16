---
id: a89cab3c-22b0-42c1-8404-9d99054874bf
title: Config
desc: ''
updated: 1609368770896
created: 1597895569675

---


### target
- [[Versions|lang.node.m.versions]]

--- 

## FAQ

### files vs include
link: https://stackoverflow.com/questions/51819184/best-practice-to-setup-tsconfig-files-vs-include
summary: includes targets collections, files target specifics

- include is a new entry added in TS 2.0, support globs

## Resources
- [json schemastore](http://json.schemastore.org/tsconfig)
- https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
- http://www.typescriptlang.org/docs/handbook/compiler-options.html


## API

## Resolution

### paths
desc: Specify path mapping to be computed relative to baseUrl option.

### rootDir

```json
"rootDir": {
  "description": "Specifies the root directory of input files. Use to control the output directory structure with --outDir.",
  "type": "string"
},
```


## Bucket

### compileOnSave
- generate all files again on saving updated `tsconfig`

###  experimentalDecorators: 
- support for es7 decorators

### files
default: false
desc: load files on startup

### lib: str[]
- desc: list of automatic library dependencies to use. will only include those dependencies. leave blank to have no automatic type inclusion
- values:  es5, es6, es2015, ...
- default:
    - if target is es5:
        - dom,es5,scripthost
    - target = es6:
        - dom,es6, dom.iterable, scripthost

- ref
  - esNext: is just a place holder for features that are on the standard track but is not in an official ES spec
  - es6: es2015
  - https://github.com/Microsoft/TypeScript/tree/master/lib

  - https://github.com/microsoft/TypeScript/issues/24082
  - To just answer the question, the difference is that import() expressions are understood in esnext, but not in es2015 (and as of TypeScript 2.9, import.meta is only understood with esnext).



### moduleResolution
- res: http://www.typescriptlang.org/docs/handbook/module-resolution.html
- d: how are modules resolved
- values:
    - classic
        - relative:
            - look for .ts file
            - look for .tsx file
        - non-rel:
            - look for module in current folder
                - walk up dir tree
    - node
        - relative
            - look for .js file
            - look for `package.json` main module in folder
            - look for index.js file in folder
        - non-rel:
            - look in `node_modules` of current folder
                - walk up tree and look in `node_modules` of each subsequent folder
                - typescript will look for `types` entry to look for `main` definition file


### target: what to compile into
- 'ES3' (default), 'ES5', or 'ES2015'

### typesRoots: string[]
- only packages under here will be looked at for type definitions
- default: node_modules/@types and typings
- eg: "typeRoots": ["./typings"]

## JS Shim

### allowJs
-  allow javascript files to be compiled

### allowSyntheticDefaultImports: bool,

- allow default imports from modules with no default export, just effect typechecking

### esModuleInterop
desc: no need to do `import * from`


## Package

### extends
- url: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html

- top-level property in tsconfig.json (alongside compilerOptions, files, include, and exclude)
- The configuration from the base file are loaded first, then overridden by those in the inheriting config file. If a circularity is encountered, we report an error.
- `files, include and exclude` from the inheriting config file overwrite those from the base config file.
- gotchas
  - include and outDir options can’t be hoisted in the root config because they are resolved relatively to the config they’re in.
  - references not inherited



- eg
```ts
// configs/base.json:
{
  "compilerOptions": {
    "noImplicitAny": true,
    "strictNullChecks": true
  }
}

// tsconfig.json
{
  "extends": "./configs/base",
  "files": [
    "main.ts",
    "supplemental.ts"
  ]
}

// tsconfig.nostrictnull.json:
{
  "extends": "./tsconfig",
  "compilerOptions": {
    "strictNullChecks": false
  }
}
```
