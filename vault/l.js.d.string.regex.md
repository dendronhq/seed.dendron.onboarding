---
id: 293d54a3-8fcf-49f6-ae0c-d5b6a0d8a57b
title: regex
desc: ''
updated: 1602803758219
created: 1595734981560
stub: false
---


## Examples

var re = /ab+c/
foo.replace(new RegExp('.md$'), '');

```js
var p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';
var regex = /dog/gi;
console.log(p.replace(regex, 'ferret'));

```

## Special Characters

```
[ \ ^ $ . | ? * + ( )

```

## === API

## Match

## Syntax

## Properties

### source: str
- string of regex

## Methods

### match
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match

- output
    - If the g flag is used, all results matching the complete regular expression will be returned, but capturing groups will not.
    - if the g flag is not used, **only the first complete match and its related capturing groups are returned** 
        - returned item will have additional properties as described below.
            - groups
                - An object of named capturing groups whose keys are the names and values are the capturing groups or undefined if no named capturing groups were defined. See Groups and Ranges for more information.
            - index
                The index of the search at which the result was found.
            - input
                A copy of the search string.

```js
let str = '<h1>Hello, world!</h1>';
let reg = /<(.*?)>/;

alert( str.match(reg) ); // Array: ["<h1>", "h1"]

// match
"foo bar".match(/foo/)
// [ 'foo', index: 0, input: 'foo bar', groups: undefined ]

// no match
"foo bar".match(/bond/)

// match with capture
> t1.match(/^p.([^.]+)./)
[ 'p.foo.', 'foo', index: 0, input: 'p.foo.bar', groups: undefined ]

```

### matchAll(regexp)
- gotcha: not supported in node (prior to 12.0)

- If a non-RegExp object obj is passed, it is implicitly converted to a RegExp by using new RegExp(obj).
- The RegExp object must have the /g flag, otherwise a TypeError will be thrown.

The matchAll() method returns an iterator of all results matching a string against a regular expression, including capturing groups.


```ts
const regexp = RegExp('foo[a-z]*','g');
const str = 'table football, foosball';
const matches = str.matchAll(regexp);

for (const match of matches) {
  console.log(`Found ${match[0]} start=${match.index} end=${match.index + match[0].length}.`);
}
// expected output: "Found football start=6 end=14."
// expected output: "Found foosball start=16 end=24."

// matches iterator is exhausted after the for..of iteration
// Call matchAll again to create a new iterator
Array.from(str.matchAll(regexp), m => m[0]);
// Array [ "football", "foosball" ]
```

## Regex

## Create

### RegExp (pattern, flags?)
- flags:
    - i: case insensitive
    - g: global match
    - m: multi line
    - s: `.` matches newlines

## Mutate

### replace
link: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@replace

### exec

The exec() method executes a search for a match in a specified string. Returns a result array, or null.

JavaScript RegExp objects are stateful when they have the global or sticky flags set (e.g. /foo/g or /foo/y). They store a lastIndex from the previous match. Using this internally, exec() can be used to iterate over multiple matches in a string of text (with capture groups), as opposed to getting just the matching strings with String.prototype.match().




### match

### split
split(reg ex or string literal)

### test
return boolean  (pattern found) 
