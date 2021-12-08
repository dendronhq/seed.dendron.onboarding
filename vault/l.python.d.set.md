---
id: 45ffe901-6aa4-4f33-92c0-8fe26adf9b27
title: Set
desc: ''
updated: 1598295141440
created: 1598295141440

source: 'https://www.pythoncheatsheet.org/blog/python-sets-what-why-how/'
---


# API

## Create

```py
>>> s1 = set([1, 2, 3])
>>> s1
{1, 2, 3}
>>> type(s1)
<class 'set'>
```

Shorthand

```py
>>> s2 = {3, 4, 5}
>>> s2
{3, 4, 5}
>>> type(s2)
<class 'set'>
>>>
```

## Get and Set

## Inspect

### in
```py
my_list = [1, 2, 3]
>>> if 2 in my_list:
...     print('Yes, this is a membership test!')
...
Yes, this is a membership test!

```

## Methods

### add

```py
>>> s = {1, 2, 3}
>>> s.add(4)
>>> s
{1, 2, 3, 4}
```

### update

```py
>>> s = {1, 2, 3}
>>> s.update([2, 3, 4, 5, 6])
>>> s
{1, 2, 3, 4, 5, 6}
```

## Delete

### remove
```
>>> s = {1, 2, 3}
>>> s.remove(3)
>>> s
{1, 2}
>>> s.remove(3)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 3
```
