---
title: "Longest Palindromic Substring"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/longest-palindromic-substring/description/)
/
[solution](https://leetcode.com/problems/longest-palindromic-substring/solution/#approach-4-expand-around-center)

## Solution in Python3
```python
class Solution:
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        max_left, max_len = 0, 0

        def expand_to(p_left, p_right):
            if p_left >= 0 and p_right < len(s) and s[p_left] == s[p_right]:                                
                expand_to(p_left - 1, p_right + 1)
            else:
                pal_len = p_right - p_left - 1
                nonlocal max_left, max_len
                if max_len < pal_len:
                    max_left = p_left + 1
                    max_len = pal_len

        for i in range(len(s)):
            expand_to(i, i)
            expand_to(i, i + 1)
        return s[max_left : max_left + max_len]
```

## Variants

### Longest possible substring centered at a certain index
- if `min(i, len(s) - 1 - i) * 2 + 1 <= max_len` need no more `expand_to(i, i)`
- if `min(i + 1, len(s) - 1 - i) * 2 <= max_len` need no more `expend_to(i, i + 1)`
- `max_len <= max(max(j, len(s) - 1 - j) * 2 + 1, max(j + 1, len(s) - 1 - j) * 2)` for `0<=j<=i`
Less expanding from the second half of `s`
[sample](https://github.com/csujedihy/lc-all-solutions/blob/master/005.longest-palindromic-substring/longest-palindromic-substring.py)