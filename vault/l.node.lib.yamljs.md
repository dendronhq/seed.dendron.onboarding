---
id: 827e7285-d8cd-4dde-a3f1-4f7cf0ef5344
title: Yamljs
desc: ''
updated: 1598636320516
created: 1598636320516

---

# Note
- this is DEPRECATED
- use [[r.node.lib.js_yaml|l.node.lib.js-yaml]]

# Res
- https://www.npmjs.com/package/yamljs

# --- Quickstart

```ts
import YAML from 'yamljs'

// parse YAML string
nativeObject = YAML.parse(yamlString);

// Generate YAML
yamlString = YAML.stringify(nativeObject, 4);

// Load yaml file using YAML.load
nativeObject = YAML.load('myfile.yml');
```

# === API

# --- yaml

### dump(obj, inline: int, spaces: int)
- params:
    - inline: depth before we start inline
    - spaces: pretty print with spaces

### stringify
- params:
    - nativeObject
    - inline 
        - integer depth to start using inline notation at */[, spaces /* @integer number of spaces to use for indentation */] ]);

  Set minimum level of depth before generating inline 
                        YAML (default: 2).
