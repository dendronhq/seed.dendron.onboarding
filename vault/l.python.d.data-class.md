---
id: ae7003d8-55c9-4039-8eb8-2048e575e463
title: data-class
desc: ''
updated: 1595706874190
created: 1595706874190
stub: false
links: |
  - https://docs.python.org/3/library/dataclasses.html
---

# Gen

This module provides a decorator and functions for automatically adding generated special methods such as __init__() and __repr__() to user-defined classes. It was originally described in PEP 557.

- examines the class to find `fields`
  - class variable that has a type annotation
  - order of the fields in all of the generated methods is the order in which they appear in the class definition

# === API

## Create

```py
class Point:
     x: int
     y: int

@dataclass
class C:
     mylist: List[Point]

p = Point(10, 20)
assert asdict(p) == {'x': 10, 'y': 20}

c = C([Point(0, 0), Point(10, 4)])
assert asdict(c) == {'mylist': [{'x': 0, 'y': 0}, {'x': 10, 'y': 4}]}
```

- default value
```py
@dataclass
class C:
    a: int       # 'a' has no default value
    b: int = 0   # assign a default value for 'b'
```


### __post__init
if any InitVar fields are defined, they will also be passed to __post_init__() in the order they were defined in the class

```py
class C:
    a: float
    b: float
    c: float = field(init=False)

    def __post_init__(self):
        self.c = self.a + self.b
```
### field
- args: `*, default=MISSING, default_factory=MISSING, repr=True, hash=None, init=True, compare=True, metadata=None`

# === Cook

### add properties

```py
from dataclasses import dataclass

@dataclass
class Test:
    _name: str="schbell"

    @property
    def name(self) -> str:
        return self._name

    @name.setter
    def name(self, v: str) -> None:
        self._name = v

t = Test()
print(t.name) # schbell
t.name = "flirp"
print(t.name) # flirp
print(t) # Test(_name='flirp')
```
