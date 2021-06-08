---
id: d4222544-573d-43ae-872f-337d1cae62dd
title: r.node.lib-immer
desc: ''
updated: 1
created: 1
stub: false
customLegacy:
  path: r.node.lib-immer
---

# Notes

# Gotchas
link: https://immerjs.github.io/immer/docs/pitfalls

- It is possible to return values from producers, except, it is not possible to return undefined that way, as it is indistinguishable from not updating the draft at all! If you want to replace the draft with undefined, just return nothing from the producer.

