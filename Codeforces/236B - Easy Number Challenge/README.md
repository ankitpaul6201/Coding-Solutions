# Easy Number Challenge

## Problem Information
- **Problem Number:** 236B
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/236/B)
- **Difficulty:** Unknown
- **Tags:** *None*
- **Language:** C++23 (GCC 14-64, msys2)
- **Runtime:** 156 ms
- **Memory:** 200 KB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Problem statement can be viewed on Codeforces.





---

## Solution
```cpp
#include <cmath>
#include <iostream>

#define MAX 1000001

using namespace std;

int main(int argc, char ** argv) {
    int a, b, c, ans = 0;
    cin >> a >> b >> c;
    int D[MAX] = {1, 1};
    for (int i = 1; i < a + 1; i++) {
        for (int j = 1; j < b + 1; j++) {
            for (int k = 1; k < c + 1; k++) {
                int l = i * j * k;
                if (!D[l]) {
                    long double sqi = sqrtl(l);
                    int sum = 0;
                    for (int m = 2; m < (int) sqi + 1; m++) {
                        if (!(l % m)) {
                            if (sqi == m) {
                                sum++;
                                continue;
                            }
                            sum += 2;
                        }
                    }
                    D[l] = sum + 2;
                }
                ans += D[l];
            }
        }
    }
    cout << ans % (1 << 31) << endl;
    return 0;
}
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
