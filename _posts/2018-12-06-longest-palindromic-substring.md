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

        def expand_to(ex_l, ex_r):
            # left/right expanding pointer
            if ex_l >= 0 and ex_r < len(s) and s[ex_l] == s[ex_r]:
                expand_to(ex_l - 1, ex_r + 1)
            else:
                pal_len = ex_r - ex_l - 1
                nonlocal max_left, max_len
                if max_len < pal_len:
                    max_left = ex_l + 1
                    max_len = pal_len

        for i in range(len(s)):
            expand_to(i, i)
            expand_to(i, i + 1)
        return s[max_left : max_left + max_len]
```

## Variants

### Longest possible substring centered at a certain index
Stop unnecessary expansion from the second half of `s`. [sample](https://github.com/csujedihy/lc-all-solutions/blob/master/005.longest-palindromic-substring/longest-palindromic-substring.py)

### Manacher’s Algorithm
Finds the longest palindromic substring in linear time. [sample](https://articles.leetcode.com/longest-palindromic-substring-part-ii/)