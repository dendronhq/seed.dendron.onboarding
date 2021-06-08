---
id: 92dbf2df-6411-4460-9fbd-3c5fb907a005
title: Version
desc: ''
updated: 1600019385619
created: 1600019385619
stub: false
---


# 2.x
# 2.7.11:
- created: 2015-12-05
  
 - note: last verison of python

# 2.7.10:
- created: 2015-05-23

# 3.x

## Gotcha
- dictionary return views instead of objects
    - eg. `adict.values()` does not return a list so indexing won't work

## Major
- strings unicode by default
- unicode and byte separation
- exception chaining
    - in python2, top level exception can swallow children exception
    - can use `raise exception from e` syntax to expliclitly show where exception is coming from
- function annotation
- syntax for keyword only arguments
- extended tuple unpacking
- non-local variable declaration

### Syntax
- `yield from` syntax
-  coroutines
- unicode variable names
- function annotations
    - puts them in __annotations__ dictionary
- `@` for matrix multiplication, using __matmul__ slot

### Libraries
- faulthandler: displays traceback even if python dies via segfault
- ipaddress
- functools.lru_cache
- enum
- pathlib
    - Path('/etc/) / "test_file.txt"


## Minor
- `thread` renamed to `_thread`
- no more implicit relative imports

  from base import BaseThing # doesn't work
  from .base import BaseThing

- new style classes by default
- print is a function
- division of two integers can result in a float (used to always be integer)
- range has same lazy evaluation as python2 xrange
- range hasa __contains__ attribute which speeds up `in` operation
- exceptions need parenthensis (like print)
    - old: raise IOError, "file error"
    - new: raise IOError("file error")
- exception need to use `as` syntax
    - old: raise IOError, err
    - new: raise IOError as err
- remove `next` instance function in python 3
- list comprehension doesn't leak to global namespace
    - old:
        i = 1
        [i for i in xrage(5)]
        print(i) # 4
    - new:
        i = 1
        [i for i in xrage(5)]
        print(i) # 1
- TypeError raised when comparing unorderable types
- `input` always stores input as string
    - old version used to convert based on user input
- common functions return iterables/generators instead of lists
    - eg: zip, map, filter, dict methods, range
- banker rounding: in case of tie, round up to nearest digit
- better tuple unpacking

    - a, b, *rest = range(10)
    - a, *rest, b :=
    - *rest, a, b
- keyword only arguments
    - use '*' to say no more args collecting

        def sum(a, b, *, biteme=False):
            pass

    - raise type error otherwise
- more fine grained OSError children
- can't compare everything to everything

# 3.5.0
- url: https://docs.python.org/3/whatsnew/3.5.html
- created: 2015-09-13
- changes: |
    - pep484: typing module
    - pep492: coroutines w/async and await syntax
    - pep465: a new matrix multiplication operator: a @ b.

# 3.6.0

- pep498: Literal String Interpoliation
```python
name = "Fred"
f"He said his name is {name}."

```

# 3.7.0
- release: 2018-06-27
- features: |
  - pep 540: utf8 mode, always use utf8
  - pep 553: built in breakpoint function, like js `debugger` statement
  - pep 557: data classes, simple classes that serve to create data
  - pep 560: support for typing module and generic types
  - pep 5767: context variables, used for async, need when storing vars that happen on the same thread

# 3.7.1
- release: 2018-10-20
- desc: first maintenance release of 3.7
