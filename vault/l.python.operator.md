---
id: 5f712ff2-e49d-4d90-9dba-185f1925ecc8
title: Operator
desc: ''
updated: 1600019385618
created: 1600019385618

---

# Equal

## value

- `==` operator

## reference

- `is` keyword

# Scope

## global
- use global keyword

```python
def local_func():
    global foo
    foo = 3

print(foo) # 3
```

# Destructure

## array

```python
head, *body, tail = range(5)
print(head, body, tail)
# 0 [1, 2, 3] 4
```
