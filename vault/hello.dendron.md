---
id: YDzohtjsx6miOafjsQGpm
title: Dendron
desc: ''
updated: 1639083522206
created: 1639083437552
---

## Hierarchies

Dendron organizes your notes into hierarchies. These are `.` delimited markdown files. 

## Example
Below is a hypothetical hierarchy for a file tree:

```
.
└── project1/
    ├── project1/designs/
    │   └── project1/designs/promotion.png
    ├── project1/paperwork/
    │   └── project1/paperwork/legal.md
    └── project1/tasks/
        ├── project1/tasks/task1.md
        └── project1/tasks/task2.md
```

The same hierarchy in Dendron would look like the following:

```
.
├── project1.md
├── project1.designs.md
├── project1.designs.promotion.md
├── project1.paperwork.md
├── project1.paperwork.legal.md
├── project1.tasks.md
├── project1.tasks.task1.md
└── project1.tasks.task2.md
```

