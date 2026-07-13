# Cifera

## Problem Information
- **Problem Number:** 114A
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/114/A)
- **Difficulty:** Unknown
- **Tags:** *None*
- **Language:** Python 2
- **Runtime:** 124 ms
- **Memory:** 0 KB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Problem statement can be viewed on Codeforces.





---

## Solution
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
k, l, la = input(), input(), 0
la = 0
def find_root(l, k):
    global la
    if l == k:
        return True
    if l % k != 0 or l < k * k:
        return False
    la += 1
    l /= k
    return find_root(l, k)
if find_root(l, k):
    print 'YES'
    print la
else:
    print 'NO'
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
