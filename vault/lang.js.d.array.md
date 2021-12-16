---
id: 68c5e2f5-f3bd-4527-bde8-ec6d66889381
title: Array
desc: ''
updated: 1600019385784
created: 1600019385784

---

## Gotchas
- `==` check doesn't work on arrays, use lodash _.isEqual
- sort() method mutates in place
- 'in' check doesn't work on arrays, only objects

## Cons

### join([separator = ','])
- separator default is comma
- join all elements together into a string

## Property

### length
- num elements in array

### indexOf
- -1 on no index

## Enumerate

### forEach( |elem, idx, array| )
- ecma6

### map(|elem, idx, array|, ...args?)
- req: es6
- not a funciton on object

### reduce(callback, initial?: any)
- syntax:
    callback(prev, current, currentIndex, array)

### filter(list, cb)


## Methods
### concat
- Returns new array with this array and other array

### fill(value, [start], [end])
- fill array with `value`

### pop 
- remove last element

### push

adds one or more elements to end and return new length

### shift

remove first element of array

### slice(begin:int, end?:int)
- param:
    - begin: zero based index to start extraction
    - end: go up to but not including end #gotcha

select parts of array

```
t1 = [1,2,3]
t1.slice(1) //[2,3]
t1.slice(0, 1) //[1]
t1.slice(1, 2) // [2,3]
```