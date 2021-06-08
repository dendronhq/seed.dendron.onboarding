---
id: bfc697ea-34d4-4b1f-8e27-e902c3485c6b
title: Lib
desc: ''
updated: 1596901366746
created: 1596901366746
stub: false
---


# Quickstart

- setup
```
mkdir -p packaging_tutorial/example_pkg
touch !$/__init__.py
cd packaging_tutorial
```

- create
```
├── README.md
├── example_pkg
│   └── __init__.py
├── setup.py
└── tests
```

```
touch README.md
touch setup.py
mkdir tests
```

- setup.py
```py
import setuptools

with open("README.md", "r") as fh:
    long_description = fh.read()

setuptools.setup(
    name="example-pkg-YOUR-USERNAME-HERE", # Replace with your own username
    version="0.0.1",
    author="Example Author",
    author_email="author@example.com",
    description="A small example package",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="https://github.com/pypa/sampleproject",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.7.5',
)
```

- check
```bash
python3 setup.py sdist bdist_wheel

```

# Cook
### uninstall develop
```
python setup.py develop --uninstall
```
