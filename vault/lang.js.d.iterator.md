---
id: 29267434-56e0-4141-87ee-3d291701b9c5
title: Iterator
desc: ''
updated: 1604712486609
created: 1604712486609
---

# Generator

```
function* idMaker() {
  var index = 0;
  while(true)
    yield index++;
}

var gen = idMaker();

```