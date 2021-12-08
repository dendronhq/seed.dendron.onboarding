---
id: 5ff04d71-4e12-4d12-bbbb-d671e78ff6d8
title: cli
desc: ''
updated: 1596142521522
created: 1596142521522

---

# Synposis

```
node [options] [v8-options] [-e string | script.js | -] [--] [arguments ...]
node inspect [-e string | script.js | - | <host>:<port>] ...
node [--v8-options]
```

# Env

- NODE_OPTIONS {options}
    - A space-separated list of command-line options, which are interpreted as if they had been specified on the command-line before the actual command (so they can be overridden). Node.js will exit with an error if an option that is not allowed in the environment is used, such as --print or a script file.
