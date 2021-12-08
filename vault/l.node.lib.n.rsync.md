---
id: 3856f610-8d65-462f-bf13-21b945c979b4
title: Rsync
desc: ''
updated: 1597856237082
created: 1597856237082

links: |
  - https://github.com/mattijs/node-rsync#readme
---



## Usage

```
var Rsync = require('rsync');

// Build the command
var rsync = new Rsync()
  .shell('ssh')
  .flags('az')
  .source('/path/to/source')
  .destination('server:/path/to/destination');

// Execute the command
rsync.execute(function(error, code, cmd) {
    // we're done
});
```

## Options

## Shorthands
- delete()
