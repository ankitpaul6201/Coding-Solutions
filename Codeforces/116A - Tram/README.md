# Tram

## Problem Information
- **Problem Number:** 116A
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/116/A)
- **Difficulty:** Unknown
- **Tags:** *None*
- **Language:** Python 2
- **Runtime:** 156 ms
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
import sys
stdin = sys.stdin.read().splitlines()
del stdin[0]
c = 0
p = 0
for v in stdin:
    o, i = map(int, v.split())
    p += i - o
    c = max(c, p)
print(str(c))
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
