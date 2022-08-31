---
id: fe683a58-f8dc-4b41-b754-609bdfe6540f
title: Byebug
desc: ''
updated: 1596650455981
created: 1596650455981
---

```
bundle add byebug --group "development, test"

```

```rb
def index
  byebug
  @articles = Article.find_recent
end

```
