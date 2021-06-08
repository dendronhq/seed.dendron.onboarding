---
id: fc01f4d0-6a6a-4da2-ba45-3b9f33bf2da9
title: Lib-debug
desc: ''
updated: 1607713169603
created: 1598636166725
stub: false
url: 'https://github.com/visionmedia/debug'
---

## Gotcha
- by default, log files go to stdout, not stderr

## Res
- https://www.npmjs.com/package/debug

```
var debug = require('debug')('http')
  , http = require('http')
  , name = 'My App';

```

## API

## ENV
- tags: config

- environment variables beginning with DEBUG_ end up being converted into an Options object that gets used with %o/%O formatters

DEBUG   Enables/disables specific debugging namespaces.
DEBUG_HIDE_DATE     Hide date from debug output (non-TTY).
DEBUG_COLORS    Whether or not to use colors in the debug output.
DEBUG_DEPTH     Object inspection depth.
DEBUG_SHOW_HIDDEN   Shows hidden properties on inspected objects.

## Related
- https://nodejs.org/api/util.html#util_util_inspect_object_options

## === Cook

## Use multiple debug statements

DEBUG=metalsmith:*,noah-cli

## Go to stdout

```
var debug = require('debug');
var error = debug('app:error');

// by default stderr is used
error('goes to stderr!');

var log = debug('app:log');
// set this namespace to log via console.log
log.log = console.log.bind(console); // don't forget to bind to console!
log('goes to stdout');
error('still goes to stderr!');

// set all output to go via console.info
// overrides all per-namespace log settings
debug.log = console.info.bind(console);
error('now goes to stdout via console.info');
log('still goes to stdout, but via console.info now');

```

## === Meta

```
createDebug(namespace):

    func debug {
        curr = ts()
        ...

        args = [...arguments]

        args[0] = coerce(args[0]) // check if its an `Error`

        if type(args[0]) != string:
            args.unshift('%O')

    }


    return debug;

```
