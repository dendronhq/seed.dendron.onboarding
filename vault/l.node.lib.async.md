---
id: b287d4db-4e35-425d-a536-9a9fc3d4cdf8
title: Lib-async
desc: ''
updated: 1
created: 1

---

# Details
- async functionality

# FAQ
- using `await` on async function without final callback results in suspension
- using a async function for iteree works
    - eg. `await mapLimit(aList, 10, async func)`

# Res
- https://caolan.github.io/async/

## Control Flow

### series(task, cb?): Promise
- run tasks in series
- return: promise if no cb is passed

```
 import _async from 'async';

 let tasks = [
   async function(cb) {
     const val1 = await Promise.resolve(1)
     console.log({val1});
     cb(null, val1)
   },
   async function(cb) {
     const val2 = await Promise.resolve(2)
     console.log({val2});
     cb(null, val2)
   }
 ]

 async function main() {
1  let out = await _async.series(tasks, (err, res) => {
     console.log({err, res});
     console.log({status: 'done async cb'});
   })
   console.log({status: 'done main'});
 }

 main()

// output
{ val1: 1 }
{ status: 'done main' }
{ val2: 2 }
{ err: null, res: [ 1, 2 ] }
{ status: 'done async cb' }

```

### mapLimit

```
var async = require('async')
var {mapLimit} = async

 var allDomains = [
     'dendron0',
     'dendron1',
     'dendron2',
     'dendron3',
     'dendron4',
     'dendron5',
     'dendron6',
     'dendron7',
     'dendron8',
     'dendron9',
     'dendron10',
     'dendron11',
     'dendron12',
     'dendron13',
     'dendron14',
     'dendron15',
     'dendron16',
     'dendron17',
     'dendron18',
     'dendron19',
     'dendron20',
     'dendron21',
     'dendron22',
     'dendron23',
     'dendron24',
     'dendron25',
     'dendron26',
     'dendron27',
     'dendron28',
     'dendron29' ]

  // normal version
  mapLimit(allDomains, 3, (ent, cb) => {
    console.log({ent});
    setTimeout(()=>{
      cb(null, ent)
    }, Math.random() * 3000)
  })

  // async version
  mapLimit(allDomains, 3, async (ent) => {
    console.log({ctx: "start", ent});
    return new Promise( (resolve) => {
        setTimeout(()=>{
            console.log({ctx: "fin", ent});
            resolve(ent)
        }, Math.random() * 3000)
    })
  }, (err, contents) => {
    console.log({ctx: "done", err, contents})
  })

     [ 'dendron0',
     'dendron1',
     'dendron2',
     'dendron3',
     'dendron4',
     'dendron5',
     'dendron6',
     'dendron7',
     'dendron8',
     'dendron9',
     'dendron10',
     'dendron11',
     'dendron12',
     'dendron13',
     'dendron14',
     'dendron15',
     'dendron16',
     'dendron17',
     'dendron18',
     'dendron19',
     'dendron20',
     'dendron21',
     'dendron22',
     'dendron23',
     'dendron24',
     'dendron25',
     'dendron26',
     'dendron27',
     'dendron28',
     'dendron29' ],

```
