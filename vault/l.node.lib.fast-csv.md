---
id: 111b491c-08a2-491d-8ec9-8dfd4f473563
title: Fast-csv
desc: ''
updated: 1599245212022
created: 1599245212022
stub: false
links: |
  - https://c2fo.io/fast-csv/docs/introduction/getting-started
---


# Quickstart

```ts
import * as csv from 'fast-csv';

const csvStream = csv.format({ headers: true });

csvStream.pipe(process.stdout).on('end', () => process.exit());

csvStream.write({ header1: 'row1-col1', header2: 'row1-col2' });
csvStream.write({ header1: 'row2-col1', header2: 'row2-col2' });
csvStream.write({ header1: 'row3-col1', header2: 'row3-col2' });
csvStream.write({ header1: 'row4-col1', header2: 'row4-col2' });
csvStream.write({ header1: 'row5-col1', header2: 'row5-col2' });
csvStream.end();
```

# Parsing

## Options
