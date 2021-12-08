---
id: 76e090e8-578f-48d3-8c28-8ad2234848bc
title: Operator
desc: ''
updated: 1600019385816
created: 1600019385816

---

# Operator

## Create
- creation is a two step process: __new__ & __init__
- creating a private variable is the same as __var

- __init__
- __new__:  called when function is first created

## Compare
- __eq__  
- __lt__
- __le__
- __ne__
- __ge__
- __gt__
- __and__ 
- __iand__ 
- __rand__ 
- __or__
- __ior__

## Inspect
 - isinstance():   checks whether attribute is an instance of something else
 - self.__class__.__name__ : name of class

 # Eg

```python
# Create a class
x = MyClass()


# Define class
class MyClass:
    """A simple example class"""

    i = 12345

    def __init__(self):
        self.data = []

    def f(self):
        return 'hello world'
```
