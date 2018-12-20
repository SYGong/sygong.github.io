---
title: "Roman to Integer"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/longest-common-prefix/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if len(strs) == 0:
            return ''
        for i in range(len(strs[0])):
            for j in range(1, len(strs)):
                if (len(strs[j]) <= i 
                    or strs[0][i] != strs[j][i]):
                    return strs[0][:i]
        return strs[0]
```
I am lucky to get
> Runtime: **120 ms**, faster than **99.54%** of Python3 online submissions for Roman to Integer.

Alternatively, aliasing `max_val` by `prev_val`, which means the value of previous symbol when we traverse `s` reversely. It just happened that `prev_val == max_val` because subtractions are restricted in roman numeral after all.

## Variants

### Left to right
Peek next symbol. [sample1](https://github.com/csujedihy/lc-all-solutions/blob/master/013.roman-to-integer/roman-to-integer.py) [sample2](https://www.geeksforgeeks.org/converting-roman-numerals-decimal-lying-1-3999/)

