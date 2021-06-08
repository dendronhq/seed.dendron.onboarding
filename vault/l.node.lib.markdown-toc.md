---
id: 9e372653-fbb9-47dd-8880-c3c6c53e2c33
title: Markdown-toc
desc: ''
updated: 1603167957573
created: 1603167932710
sources:
  - name: ""
    url: https://github.com/jonschlinkert/markdown-toc
    license: ""
---

var Remarkable = require('remarkable');
var toc = require('markdown-toc');

function render(str, options) {
  return new Remarkable()
    .use(toc.plugin(options)) // <= register the plugin
    .render(str);
}