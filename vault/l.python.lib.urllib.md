---
id: 8424a444-8297-420e-9017-a287878bbe35
title: urllib
desc: ''
updated: 1595721177247
created: 1595721177247
stub: false
---


# urllib.parse.urlparse(urlstring, scheme='', allow_fragments=True)

```
>>> from urllib.parse import urlparse
>>> o = urlparse('http://www.cwi.nl:80/%7Eguido/Python.html')
>>> o   
ParseResult(scheme='http', netloc='www.cwi.nl:80', path='/%7Eguido/Python.html',
            params='', query='', fragment='')

```
