# Zigzag Conversion

## Problem Information
- **Problem Number:** 6
- **Platform:** [LeetCode](https://leetcode.com/problems/zigzag-conversion/)
- **Difficulty:** Medium
- **Tags:** `String`
- **Language:** C++
- **Runtime:** 12 ms
- **Memory:** 14.2 MB
- **Submission Date:** 2026-07-13

---

## Problem Statement
The string `"PAYPALISHIRING"` is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P   A   H   N
A P L S I I G
Y   I   R

```

And then read line by line: `"PAHNAPLSIIGYIR"`

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows);

```

**Example 1:**

**Input:** s = "PAYPALISHIRING", numRows = 3
**Output:** "PAHNAPLSIIGYIR"

```

**Example 2:**

**Input:** s = "PAYPALISHIRING", numRows = 4
**Output:** "PINALSIGYAHRPI"
**Explanation:**
P     I    N
A   L S  I G
Y A   H R
P     I

```

**Example 3:**

**Input:** s = "A", numRows = 1
**Output:** "A"

```

**Constraints:**

	- `1 <= s.length <= 1000`

	- `s` consists of English letters (lower-case and upper-case), `&#39;,&#39;` and `&#39;.&#39;`.

	- `1 <= numRows <= 1000`

### Examples
**Example 1:**
```
P   A   H   N
A P L S I I G
Y   I   R
```

**Example 2:**
```
string convert(string s, int numRows);
```

**Example 3:**
```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

**Example 4:**
```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:
P     I    N
A   L S  I G
Y A   H R
P     I
```

**Example 5:**
```
Input: s = "A", numRows = 1
Output: "A"
```



### Constraints
- 1 <= s.length <= 1000
- s consists of English letters (lower-case and upper-case), ',' and '.'.
- 1 <= numRows <= 1000




---

## Solution
```cpp
class Solution {
public:
    string convert(string s, int numRows) {

        if (numRows == 1 || numRows >= s.size())
            return s;

        vector<string> rows(numRows);

        int currRow = 0;
        bool goingDown = false;

        for (char c : s) {

            rows[currRow] += c;

            if (currRow == 0 || currRow == numRows - 1)
                goingDown = !goingDown;

            currRow += goingDown ? 1 : -1;
        }

        string ans;

        for (string row : rows)
            ans += row;

        return ans;
    }
};
```



---
*Auto-generated using [CP Vault](https://github.com/ankit/CP-Vault).*
