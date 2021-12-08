---
id: e14770e4-8a24-4721-b892-bf586c9319a6
title: Lib
desc: ''
updated: 1596676263327
created: 1596676263327

---

# Quickstart

- file structure
```
.
├── hola.gemspec
└── lib
    └── hola.rb

```

- gemspec
```
% cat hola.gemspec
Gem::Specification.new do |s|
  s.name        = 'hola'
  s.version     = '0.0.0'
  s.date        = '2010-04-28'
  s.summary     = "Hola!"
  s.description = "A simple hello world gem"
  s.authors     = ["Nick Quaranto"]
  s.email       = 'nick@quaran.to'
  s.files       = ["lib/hola.rb"]
  s.homepage    =
    'https://rubygems.org/gems/hola'
  s.license       = 'MIT'
end
```

# Build
