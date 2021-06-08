---
id: 5b47eacf-475a-4c2f-b004-e15cbe63a90f
title: Csv
desc: ''
updated: 1600019385809
created: 1600019385809
stub: false
---


# DictReader

csv.DictReader(csvfile, fieldnames=None, restkey=None, restval=None, dialect='excel', *args, **kwds)

## Quickstart
```python
import csv
with open('names.csv') as csvfile:
...     reader = csv.DictReader(csvfile)
...     for row in reader:
...         print(row['first_name'], row['last_name'])
```
