---
id: 1e2955a1-fc95-4c82-912a-8e0871a0ac7d
title: Dict
desc: ''
updated: 1600019385810
created: 1600019385810
stub: false
---

## Gotchas
- if try to retrieve non-existing key using '[]' syntax, will throw `KeyError`
  - diff from ruby which will return `nil`
  - to return None, use `{dict}.get(...)`

## API

## Create

```py
## using `dict`
dict(sape=4139, guido=4127, jack=4098)

## list comprehension
d = {key: value for (key, value) in iterable}
## eg.
{x: x**2 for x in (2, 4, 6)}
```

## Get and Set
```py
my_dictionary = {"song": "Estranged", "artist": "Guns N' Roses"}
print(my_dictionary["song"])
my_dictionary["song"] = "Paradise City"
```

## Operator

### Inspect

### has_key(key)

### Iterate

#### items

```python
for key, value in d.items():
```
#### iteritems()
#### iterkeys()
#### itervalues()


## Mutate

### update
