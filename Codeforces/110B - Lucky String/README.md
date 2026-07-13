# Lucky String

## Problem Information
- **Problem Number:** 110B
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/110/B)
- **Difficulty:** Unknown
- **Tags:** *None*
- **Language:** Python 2
- **Runtime:** 186 ms
- **Memory:** 0 KB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Problem statement can be viewed on Codeforces.





---

## Solution
```python
#!/usr/bin/python
# -*- coding: utf-8 -*-

from __future__ import print_function
p = lambda x: print(x, end="")
for i in xrange(input()):
    if i % 4 == 0:
        p("a")
    elif i % 4 == 1:
        p("b")
    elif i % 4 == 2:
        p("c")
    else:
        p("d")
print()
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
