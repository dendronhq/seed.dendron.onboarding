---
id: fe567c0e-06a2-4485-9054-c46a31d02c42
title: Standard version
desc: ''
updated: 1593888333378
created: 1593888333378
stub: false
links: |
  - https://github.com/conventional-changelog/standard-version
---


# Quickstart

```
npm i --save-dev standard-version
```

- package
```json
{
  "scripts": {
    "release": "standard-version"
  }
}
```

```
npm run release -- --first-release

npm run release

```

# === Conventional Commits
link: https://www.conventionalcommits.org/en/v1.0.0

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

# Details
- fix: a commit of the type fix patches a bug in your codebase (this correlates with PATCH in semantic versioning).
- feat: a commit of the type feat introduces a new feature to the codebase (this correlates with MINOR in semantic versioning).
- BREAKING CHANGE: a commit that has a footer BREAKING CHANGE:, or appends a ! after the type/scope, introduces a breaking API change (correlating with MAJOR in semantic versioning). A BREAKING CHANGE can be part of commits of any type.
- types other than fix: and feat: are allowed, for example @commitlint/config-conventional (based on the the Angular convention) recommends build:, 
    - chore:
    - ci:
    - docs:
    - style:
    - refactor:
    - perf:
    - test:
    - others.
- footers other than BREAKING CHANGE: <description> may be provided and follow a convention similar to git trailer format.

- A **scope** may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., feat(parser): add ability to parse arrays.

# Examples

### Commit message with description and breaking change footer

```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files


```

# Use

### dry run

```
npm run release -- --dry-run
```

### override aut oversion bump

Suppose the last version of your code is 1.0.0, you've only landed fix: commits, but you would like your next release to be a minor. Simply run the following:


```
# npm run script
npm run release -- --release-as minor
# Or
npm run release -- --release-as 1.1.0

```


### specify custom range
- need to muck with code
  - https://github.com/conventional-changelog/standard-version/issues/205
