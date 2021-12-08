---
id: f2cec6e9-6568-4898-961e-4641dba46d8f
title: Import
desc: ''
updated: 1600019385816
created: 1600019385816

---


# 
# import

```py
__import__(name[, globals[, locals[, fromlist[, level]]]])

```
- @syntax:
name String: module name

# Dynamic import
mod = __import__(mod_path, fromlist=[mod_name])
klass = getattr(mod, mod_name)
ac = klass(config, args)

# Reload import
url: https://stackoverflow.com/questions/2918898/prevent-python-from-caching-the-imported-modules
req: python3

```py
import moduleA, moduleB
from imp import reload
reload (moduleB)

```
# relative import
src: journal.2020.05.11.md


- https://stackoverflow.com/questions/16981921/relative-imports-in-python-3

- Relative imports use a module's __name__ attribute to determine that module's position in the package hierarchy
- If the module's name does not contain any package information (e.g. it is set to '__main__') then relative imports are resolved as if the module were a top level module, regardless of where the module is actually located on the file system.
- ... relative imports rely on __name__ to determine the current module's position in the package hierarchy. In a main module, the value of __name__ is always '__main__', so explicit relative imports will always fail (as they only work for a module inside a package)
- and to address the issue, PEP 366 introduced the top level variable __package__:
    - By adding a new module level attribute, this PEP allows relative imports to work automatically if the module is executed using the -m switch
    - relative imports will be based on this attribute rather than the module __name__ attribute.
- the parent module must be explicitly absolute-imported before performing relative import.
