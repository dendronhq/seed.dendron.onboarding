---
id: 88c34689-f179-4510-bc64-f0ccc861e202
title: r.node.net
desc: ''
updated: 1
created: 1

customLegacy:
  path: r.node.net
---



# === Use

### Make a request

```js
const endpoint = "localhost:"
const options = {
  host: url,
  port: 443,
  path: '/cron/?type=drupal',
  method: 'GET'
};

http.request(options, function(res) {
  console.log('STATUS: ' + res.statusCode);
  console.log('HEADERS: ' + JSON.stringify(res.headers));
  res.setEncoding('utf8');
  res.on('data', function (chunk) {
    console.log('BODY: ' + chunk);
  });
}).end();

```
