# Regular Expression Matching

## Problem Information
- **Problem Number:** 10
- **Platform:** [LeetCode](https://leetcode.com/problems/regular-expression-matching/)
- **Difficulty:** Hard
- **Tags:** `String` `Dynamic Programming` `Recursion`
- **Language:** C++
- **Runtime:** 0 ms
- **Memory:** 9.2 MB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Given an input string `s` and a pattern `p`, implement regular expression matching with support for `&#39;.&#39;` and `&#39;*&#39;` where:

	- `&#39;.&#39;` Matches any single character.​​​​

	- `&#39;*&#39;` Matches zero or more of the preceding element.

Return a boolean indicating whether the matching covers the entire input string (not partial).

**Example 1:**

**Input:** s = "aa", p = "a"
**Output:** false
**Explanation:** "a" does not match the entire string "aa".

```

**Example 2:**

**Input:** s = "aa", p = "a*"
**Output:** true
**Explanation:** &#39;*&#39; means zero or more of the preceding element, &#39;a&#39;. Therefore, by repeating &#39;a&#39; once, it becomes "aa".

```

**Example 3:**

**Input:** s = "ab", p = ".*"
**Output:** true
**Explanation:** ".*" means "zero or more (*) of any character (.)".

```

**Constraints:**

	- `1 <= s.length <= 20`

	- `1 <= p.length <= 20`

	- `s` contains only lowercase English letters.

	- `p` contains only lowercase English letters, `&#39;.&#39;`, and `&#39;*&#39;`.

	- It is guaranteed for each appearance of the character `&#39;*&#39;`, there will be a previous valid character to match.

### Examples
**Example 1:**
```
Input: s = "aa", p = "a"
Output: false
Explanation: "a" does not match the entire string "aa".
```

**Example 2:**
```
Input: s = "aa", p = "a*"
Output: true
Explanation: '*' means zero or more of the preceding element, 'a'. Therefore, by repeating 'a' once, it becomes "aa".
```

**Example 3:**
```
Input: s = "ab", p = ".*"
Output: true
Explanation: ".*" means "zero or more (*) of any character (.)".
```



### Constraints
- 1 <= s.length <= 20
- 1 <= p.length <= 20
- s contains only lowercase English letters.
- p contains only lowercase English letters, '.', and '*'.
- It is guaranteed for each appearance of the character '*', there will be a previous valid character to match.




---

## Solution
```cpp
class Solution {
public:
    bool isMatch(string s, string p) {

        int m = s.size();
        int n = p.size();

        vector<vector<bool>> dp(m + 1, vector<bool>(n + 1, false));

        dp[0][0] = true;

        // Handle patterns like a*, a*b*, a*b*c*
        for (int j = 2; j <= n; j++) {
            if (p[j - 1] == '*')
                dp[0][j] = dp[0][j - 2];
        }

        for (int i = 1; i <= m; i++) {

            for (int j = 1; j <= n; j++) {

                if (p[j - 1] == '.' || p[j - 1] == s[i - 1]) {

                    dp[i][j] = dp[i - 1][j - 1];

                }
                else if (p[j - 1] == '*') {

                    // Zero occurrence
                    dp[i][j] = dp[i][j - 2];

                    // One or more occurrences
                    if (p[j - 2] == '.' || p[j - 2] == s[i - 1])
                        dp[i][j] = dp[i][j] || dp[i - 1][j];
                }
            }
        }

        return dp[m][n];
    }
};
```



---
*Auto-generated using [CP Vault](https://github.com/ankit/CP-Vault).*
