# Two Digit Strings

## Problem Information
- **Problem Number:** 2242D
- **Platform:** [Codeforces](https://codeforces.com/problemset/problem/2242/D)
- **Difficulty:** Unknown
- **Tags:** *None*
- **Language:** C++23 (GCC 14-64, msys2)
- **Runtime:** 156 ms
- **Memory:** 94500 KB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Problem statement can be viewed on Codeforces.





---

## Solution
```cpp
#include <bits/stdc++.h>
using namespace std;

void upd(int &x, int y) {
    if (x < y) x = y;
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int T;
    cin >> T;

    while (T--) {
        string a, b;
        cin >> a >> b;

        int n = a.size();
        int m = b.size();

        vector<int> pa(n + 1), pb(m + 1);

        for (int i = 0; i < n; i++)
            pa[i + 1] = (pa[i] + (a[i] - '0')) % 10;

        for (int i = 0; i < m; i++)
            pb[i + 1] = (pb[i] + (b[i] - '0')) % 10;

        n++;
        m++;

        if (pa.back() != pb.back()) {
            cout << -1 << '\n';
            continue;
        }

        vector<vector<int>> dp(n + 1, vector<int>(m + 1, 0));

        for (int i = 0; i <= n; i++) {
            for (int j = 0; j <= m; j++) {
                if (i < n) upd(dp[i + 1][j], dp[i][j]);
                if (j < m) upd(dp[i][j + 1], dp[i][j]);

                if (i < n && j < m && pa[i] == pb[j]) {
                    upd(dp[i + 1][j + 1], dp[i][j] + 1);
                }
            }
        }

        cout << dp[n][m] - 1 << '\n';
    }

    return 0;
}
```



---
*Auto-generated using [CP Vault](https://github.com/ankitpaul6201/CP-VAULT).*
