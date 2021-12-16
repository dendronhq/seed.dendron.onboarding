---
id: cb127ce0-1d81-4a93-941d-b40e6a0e5649
title: Abstract
desc: ''
updated: 1600019385815
created: 1600019385815

---


## Abstract
```python
from abc import ABCMeta, abstractmethod

class MyIterable:
    __metaclass__ = ABCMeta

    @abstractmethod
    def __iter__(self):
        while False:
            yield None

    def get_iterator(self):
        return self.__iter__()

    @classmethod
    def __subclasshook__(cls, C):
        if cls is MyIterable:
            if any("__iter__" in B.__dict__ for B in C.__mro__):
                return True
        return NotImplemented

```
