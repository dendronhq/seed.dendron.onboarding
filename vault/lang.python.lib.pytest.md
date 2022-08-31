---
id: f06e6035-dfe0-4f5c-bd8f-28568e2c02a3
title: pytest
desc: ''
updated: 1638986297050
created: 1595705153631
---


# Usage

```py
# content of test_sample.py
def inc(x):
    return x + 1


def test_answer():
    assert inc(3) == 5

```

- execute
```bash
=========================== test session starts ============================
platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
cachedir: $PYTHON_PREFIX/.pytest_cache
rootdir: $REGENDOC_TMPDIR
collected 1 item

test_sample.py F                                                     [100%]

================================= FAILURES =================================
_______________________________ test_answer ________________________________

    def test_answer():
>       assert inc(3) == 5
E       assert 4 == 5
E        +  where 4 = inc(3)

test_sample.py:6: AssertionError
========================= short test summary info ==========================
FAILED test_sample.py::test_answer - assert 4 == 5
============================ 1 failed in 0.12s =============================
```

