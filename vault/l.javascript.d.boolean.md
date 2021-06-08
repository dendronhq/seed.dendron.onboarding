---
id: 57a6d1ad-8d77-49ca-b7b7-c4f0c938d2ef
title: Boolean
desc: ''
updated: 1598047083875
created: 1598047083875
stub: false
source: >-
  https://developer.mozilla.org/en-US/docs/Glossary/Truthy#:~:text=In%20JavaScript%2C%20a%20truthy%20value,type%20coercion%20in%20Boolean%20contexts.
---

# True
 All values are truthy unless they are defined as falsy (see below)

Following are all true
 ```
if (true)
if ({})
if ([])
if (42)
if ("0")
if ("false")
if (new Date())
if (-42)
if (12n)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
 ```

# False
- false, 0, -0, 0n, "", null, undefined, and NaN
