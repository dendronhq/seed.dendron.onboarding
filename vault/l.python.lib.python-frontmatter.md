---
id: ded87544-dc5c-4b94-b333-c183e10c9805
title: python-frontmatter
desc: ''
updated: 1595699791306
created: 1595699791306

links: |
  - https://pypi.org/project/python-frontmatter/
  - https://github.com/eyeseast/python-frontmatter
---


# Quickstart

```py
import frontmatter

# load
post = frontmatter.load('tests/hello-world.markdown')

# parse
with open('tests/hello-world.markdown') as f:
    metadata, content = frontmatter.parse(f.read())
```

# Cook

### write 

```py
>>> print(frontmatter.dumps(post)) # doctest: +NORMALIZE_WHITESPACE
---
excerpt: tl;dr
layout: post
title: Hello, world!
---
Well, hello there, world.

```

### write to file

```py
>>> from io import BytesIO
>>> f = BytesIO()
>>> frontmatter.dump(post, f)
>>> print(f.getvalue().decode('utf-8')) # doctest: +NORMALIZE_WHITESPACE
```
