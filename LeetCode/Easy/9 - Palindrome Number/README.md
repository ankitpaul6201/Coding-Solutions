# Palindrome Number

## Problem Information
- **Problem Number:** 9
- **Platform:** [LeetCode](https://leetcode.com/problems/palindrome-number/)
- **Difficulty:** Easy
- **Tags:** `Math`
- **Language:** C++
- **Runtime:** 4 ms
- **Memory:** 8.7 MB
- **Submission Date:** 2026-07-13

---

## Problem Statement
Given an integer `x`, return `true`* if *`x`* is a ****palindrome****, and *`false`* otherwise*.

**Example 1:**

**Input:** x = 121
**Output:** true
**Explanation:** 121 reads as 121 from left to right and from right to left.

```

**Example 2:**

**Input:** x = -121
**Output:** false
**Explanation:** From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

```

**Example 3:**

**Input:** x = 10
**Output:** false
**Explanation:** Reads 01 from right to left. Therefore it is not a palindrome.

```

**Constraints:**

	- `-2<sup>31</sup> <= x <= 2<sup>31</sup> - 1`

**Follow up:** Could you solve it without converting the integer to a string?

### Examples
**Example 1:**
```
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

**Example 2:**
```
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

**Example 3:**
```
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```



### Constraints
- -231 <= x <= 231 - 1




---

## Solution
```cpp
class Solution {
public:
    bool isPalindrome(int x) {

        if (x < 0 || (x % 10 == 0 && x != 0))
            return false;

        int reversedHalf = 0;

        while (x > reversedHalf) {
            reversedHalf = reversedHalf * 10 + x % 10;
            x /= 10;
        }

        return (x == reversedHalf || x == reversedHalf / 10);
    }
};
```



---
*Auto-generated using [CP Vault](https://github.com/ankit/CP-Vault).*
