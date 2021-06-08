---
id: b245f659-a0ec-4e39-88c2-124cefcf98cb
title: Lib-open
desc: ''
updated: 1597258522428
created: 1597258522428
stub: false
customLegacy:
  links:
    - 'https://www.npmjs.com/package/open'
---

```js
const open = require('open');
 
(async () => {
    // Opens the image in the default image viewer and waits for the opened app to quit.
    await open('unicorn.png', {wait: true});
    console.log('The image viewer app quit');
 
    // Opens the URL in the default browser.
    await open('https://sindresorhus.com');
 
    // Opens the URL in a specified browser.
    await open('https://sindresorhus.com', {app: 'firefox'});
 
    // Specify app arguments.
    await open('https://sindresorhus.com', {app: ['google chrome', '--incognito']});
})();

```

