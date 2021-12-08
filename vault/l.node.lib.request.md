---
id: 084527f1-f066-4448-8a5d-9f03afbd574d
title: node.lib-request
desc: ''
updated: 1598636172038
created: 1598636172038

excerpt: null
url: 'https://github.com/request/request'
---

# === API

### request(options, cb)
- params.options:
    - qs: querystring values
    - body: entity body for PATCH, POST and PUT requests. Must be a Buffer, String or ReadStream. If json is true, then body must be a JSON-serializable object.


# === FAQ

## Specify port number: http://stackoverflow.com/questions/31662411/specify-port-number-in-http-request-node-js

# Cook

## request

- Chaining
```
request
  .get('http://google.com/img.png')
  .on('response', function(response) {
    console.log(response.statusCode) // 200
    console.log(response.headers['content-type']) // 'image/png'
  })
  .pipe(request.put('http://mysite.com/img.png'))
```

- Regular
```
request.post(uri, (err, resp, body) => {
})

```

## response

### statusCode


# === Cook

## Downloading a file

```
var fs = require('fs'),
    request = require('request');

function (url, path, callback) {
  request({uri: url})
      .pipe(fs.createWriteStream(path))
      .on('close', function() {
        callback();
      });

```

### Download an image

```
var fs = require('fs'),
    request = require('request');

var download = function(uri, filename, callback){
  request.head(uri, function(err, res, body){
    console.log('content-type:', res.headers['content-type']);
    console.log('content-length:', res.headers['content-length']);

    request(uri).pipe(fs.createWriteStream(filename)).on('close', callback);
  });
};

download('https://www.google.com/images/srpr/logo3w.png', 'google.png', function(){
  console.log('done');
});

```
### use cookies

```
const request = request.defaults({jar: true})
request('http://www.google.com', function () {
  request('http://images.google.com')
})

```
