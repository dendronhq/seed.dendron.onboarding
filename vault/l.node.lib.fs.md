---
id: 0326a6e7-077c-45ed-bc51-8b8c5a1a66fb
title: Fs
desc: ''
updated: 1611702667133
created: 1605036195407
---


# Docs
- https://nodejs.org/api/fs.html#fs_class_fs_fswatcher

# FS

## events

### change

### close

### error

### ready

### data

## methods

### fs.watch

### fs.watchFile(filename [,options] , callback)

- options:
    - persistent: whether process should run as long as the file is bring watched (default: true)
    - recursive: whether or not the process should monitor for changes in subdirectories as well (default: false)
    - encoding: the character encoding of the filename (default: ‘utf8‘)
- cb:
    - The callback function contains two arguments (event, trigger) where event specifies the type of change that occurred (typically change or rename) and trigger specifies the file that was changed.
    - eventType is either 'rename' or 'change', and filename is the name of the file which triggered the event.

# FSWatcher
- A successful call to fs.watch() method will return a new fs.FSWatcher object.
- All fs.FSWatcher objects emit a 'change' event whenever a specific watched file is modified.

```js
// Example when handled through fs.watch() listener
fs.watch('./tmp', { encoding: 'buffer' }, (eventType, filename) => {
  if (filename) {
    console.log(filename);
    // Prints: <Buffer ...>
  }
});
```




# FAQ

### watch vs watchFile
- “Using fs.watch() is more efficient than fs.watchFile and fs.unwatchFile. fs.watch should be used instead of fs.watchFile and fs.unwatchFile when possible.”
- fs.watch() makes use of the native operating system’s methods of watching files in order to function. fs.watchFile() constantly checks for changes at fixed intervals regardless of file activity