---
title: "Longest Palindromic Substring"
tags: [LeetCode, Python3]
categories: leetcore
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
        max_start, max_len = 0, 0

        # ex_l/ex_r denotes left/right expanding pointer
        def expand_to(ex_l, ex_r):
            if ex_l >= 0 and ex_r < len(s) and s[ex_l] == s[ex_r]:
                expand_to(ex_l - 1, ex_r + 1)
            else:
                pal_len = ex_r - ex_l - 1
                nonlocal max_start, max_len
                if max_len < pal_len:
                    max_start = ex_l + 1
                    max_len = pal_len

        for i in range(len(s)):
            expand_to(i, i)
            expand_to(i, i + 1)
        return s[max_start : max_start + max_len]
```

### Time Complexity
$$O(l^2)$$, where $$l$$ is the length of `s`. 
- Each iteration of the `for` loop takes $$O(l)$$.

## Variants

### Longest possible substring centered at a certain index
Stop unnecessary expansion from the second half of `s`. [sample](https://github.com/csujedihy/lc-all-solutions/blob/master/005.longest-palindromic-substring/longest-palindromic-substring.py)

### Manacher’s Algorithm
A linear time algorithm. [sample](https://articles.leetcode.com/longest-palindromic-substring-part-ii/)