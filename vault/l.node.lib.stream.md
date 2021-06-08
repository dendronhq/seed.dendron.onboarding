---
id: 64dddfa5-df3a-41d7-8cd9-2bd40361f019
title: Stream
desc: ''
updated: 1609976798875
created: 1609976767344
---

---
# Writable

## events

### pipe

```
writer.on('pipe', (src) => {
  console.log('Something is piping into the writer.');
  assert.equal(src, reader);
});
```


