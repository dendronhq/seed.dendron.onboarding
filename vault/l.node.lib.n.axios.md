---
id: b7bcbc52-ae24-4a9c-822c-102461c374b4
title: axios
desc: ''
updated: 1595529226197
created: 1595529226197

---


## === Cook

### enable keep-alive
- https://github.com/axios/axios/issues/1846

## === API

## Create

### create([config])
- baseURL: 'https://some-domain.com/api/',
- timeout: 1000,
- headers: {'X-Custom-Header': 'foobar'}
- withCredentials: false,
    - cross-site Access-Control requests should be made using credentials<Paste>


## --- Response

## Resp
```
{
  // `data` is the response that was provided by the server
  data: {},

  // `status` is the HTTP status code from the server response
  status: 200,

  // `statusText` is the HTTP status message from the server response
  statusText: 'OK',

  // `headers` the headers that the server responded with
  // All header names are lower cased
  headers: {},

  // `config` is the config that was provided to `axios` for the request
  config: {},

  // `request` is the request that generated this response
  // It is the last ClientRequest instance in node.js (in redirects)
  // and an XMLHttpRequest instance the browser
  request: {}
}
```
