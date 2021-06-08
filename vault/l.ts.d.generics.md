---
id: 2715f9ef-8272-4eec-8e89-81d0e49ff46c
title: ts.d.generics
desc: ''
updated: 1609216779677
created: 1
stub: false
customLegacy:
  url: 'https://www.typescriptlang.org/docs/handbook/generics.html'
---

# Detail

- ts infers that items passed iin is a number
```ts
function reverse<T>(items: T[]): T[] {
    var toreturn = [];
    for (let i = items.length - 1; i >= 0; i--) {
        toreturn.push(items[i]);
    }
    return toreturn;
}

var sample = [1, 2, 3];
var reversed = reverse(sample);
console.log(reversed); // 3,2,1

// check number[]
reversed[0] = '1';     // Error!
reversed = ['1', '2']; // Error!

reversed[0] = 1;       // Okay
reversed = [1, 2];     // Okay

// check string[]
var strArr = ['1', '2'];
var reversedStrs = reverse(strArr);

reversedStrs = [1, 2]; // Error!
```

# Concepts

### Generic Constraints
- restrict generic to subset of things

### Generic Function

### Generic Class

# Use
### Generic Constraints with Defaults

```ts
export interface IScraperLink<T extends IScraperData = IScraperData> {

```
