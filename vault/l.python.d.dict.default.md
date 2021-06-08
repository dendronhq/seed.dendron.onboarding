---
id: 5de26f4a-4a40-4215-905f-153a31a8a227
title: Default
desc: ''
updated: 1600019386588
created: 1600019386588
stub: false
---


# Quickstart

```python
import collections.defaultdict
>>> s = [('yellow', 1), ('blue', 2), ('yellow', 3), ('blue', 4), ('red', 1)]
>>> d = defaultdict(list)
>>> for k, v in s:
...     d[k].append(v)
...
>>> d.items()
[('blue', [2, 4]), ('red', [1]), ('yellow', [1, 3])]

```
