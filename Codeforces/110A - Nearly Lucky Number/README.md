# Nearly Lucky Number

## Problem Information
- **Problem Number:** 110A
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/110/A)
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
#!/usr/bin/python
# -*- coding: utf-8 -*-
number = raw_input()
total = number.count("4") + number.count("7")
if total is 4 or total is 7:
    print("YES")
else:
    print("NO")
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
