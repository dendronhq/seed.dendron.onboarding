---
id: c6af4c93-5d78-4462-be06-b640ebbd4e0e
title: l.python.builtin.typing
desc: ''
updated: 1593881250648
created: 1593881250648
stub: false
customLegacy:
  min_version: 3.5
  url: 'https://docs.python.org/3/library/typing.html'
  node:
    pep: 484
---

# API
## NamedTuple

```python
class Employee(NamedTuple):
    name: str
    id: int

# same as
Employee = collections.namedtuple('Employee', ['name', 'id'])

# initialize
employee = Employee('Guido')

```

