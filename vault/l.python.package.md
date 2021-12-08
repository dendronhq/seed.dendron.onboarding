---
id: 170d6fe6-6e9f-41c1-9263-5079aa0db618
title: Packages
desc: ''
updated: 1593881250655
created: 1593881250655

customLegacy:
  links:
    - 'http://lucumr.pocoo.org/2012/6/22/hate-hate-hate-everywhere/'
    - 'https://packaging.python.org/requirements/'
    - >-
      https://stackoverflow.com/questions/6344076/differences-between-distribute-distutils-setuptools-and-distutils2
---

# Package Managers

- distribute
    - fork of setuptools, now deprecated
- distutils: standard library
    - make tarballs of python code
    - helpers
    - invoke compilers
    - did not handle metadata
        - no dep tracking
    - layout:
        - lib/
            - site-packages/
                - flask/
                - django/
    - cons:
        - no binary distribution really

- distutils2
    - combine best of distutils, setuptools and distribute
    - plan was to be include in python 3.3 as `packaging`
    - abandoned
    - changes
        - setup.py to setup.cfg
            - reason: get static info w/out running code
- distlib
    - new distutils2 project?
    - alpha
- bento
    - ?
- setuptools
    - automatically populate meta data
    - introduces `easy_install`
    - adds indirection to packaging
        - puts each package into egg folder and adds folders to python path using `pth` file
        - can also add metadata to `.egg` folder
    - layout:
        - site-packages/
            - Flask-1.0.egg/
                - flask/
            - Django-1.0.egg/
                - django/
            - easy-install.pth
    - cons:
        - lost line numbers when files where in zip
        - made `sys.path` excessively long

# concepts
- pth files:
    - each line that starts with `import` in 'pth' file is executed as python code
        - eg: http://lucumr.pocoo.org/2012/6/22/hate-hate-hate-everywhere/
    - use this to put hooks in place w/python code before interpreter runs
    - makes setuptools possible

- .egg folders
- .egg archives
- binary egg:
    - no setup.py executable
    - unpack and done
    - its platform specific

# notes
- seems like distutils doesn't have a way of specifying dependencies of dependencies
- pip did not seem to have fixed this
- if you want to specify dependencies, use setuptools
