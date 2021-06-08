---
id: 1aefe574-58f4-4536-9bae-63f85eb4e6bd
title: Cli
desc: ''
updated: 1597109464988
created: 1597109464988
stub: false
links: |
  - https://github.com/conventional-changelog/standard-version
---

## Options
-   --no-verify, -n      
    - Bypass pre-commit or commit-msg git hooks during the commit phase
-  --skip               Map of steps in the release process that should be skipped   [default: {}]
-   --path               Only populate commits made under this path                        [string]
-   --preset             Commit message guideline preset


## Details
- Retrieve the current version of your repository by looking at bumpFiles[1], falling back to the last git tag.
- bump the version in bumpFiles[1] based on your commits.
- Generates a changelog based on your commits (uses conventional-changelog under the hood).
- Creates a new commit including your bumpFiles[1] and updated CHANGELOG.
- Creates a new tag with the new version number.

## Concepts

### packageFiles

User-defined files where versions can be read from and be "bumped".
Examples: package.json, manifest.json

### bumpFiles

User-defined files where versions should be "bumped", but not explicitly read from.
Examples: package-lock.json, npm-shrinkwrap.jso

### updaters

Simple modules used for reading packageFiles and writing to bumpFiles.

## Lifecycle
- links: https://github.com/conventional-changelog/standard-version#lifecycle-scripts
