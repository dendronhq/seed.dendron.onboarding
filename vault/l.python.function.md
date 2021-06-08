---
id: 4baeb9d2-7152-4612-a817-0b3fdf2b4137
title: Function
desc: ''
updated: 1600019385617
created: 1600019385617
stub: false
---


## Args

## Var Args
```python
def foo(*args):
    ...
```
## Mixed
- keywords arguments cannot be followed by *args, will result in syntax error
  - this is fixed in python3 but no 2.x backport

- kw args after varargs are mandatory and can't be filled in by positional arguments
```python
def sortwords(*wordlist, case_sensitive=False):
    pass
```

- tell python after `b`, to let no more positional arguments
```python
def compare(a, b, *, key=None):
    ...

```


