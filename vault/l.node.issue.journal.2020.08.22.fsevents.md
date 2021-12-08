---
id: b474ab32-1040-4cde-89dc-1f8b8eb62e77
title: fsevent issue
desc: ''
updated: 1638986144923
created: 1598120430218

---

Error: `fsevents` unavailable (this watcher can only be used on Darwin)


```
npm run test -- --watch "src/drivers/file/__tests__/parser.spec.ts" "-u"`
```

# Fix
- https://stackoverflow.com/questions/52427810/error-fsevents-unavailable-this-watcher-can-only-be-used-on-darwin
- install watchmen

2020-08-22
2020-08-22
2020-08-22

2020-08-22

2020-08-22

l.node.issue.journal.2020.08.22.fsevents
