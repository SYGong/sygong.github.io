---
title: "Roman to Integer"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/roman-to-integer/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        sym_val = {"M" : 1000,
                   "D" : 500,
                   "C" : 100,
                   "L" : 50,
                   "X" : 10,
                   "V" : 5,
                   "I" : 1}
        int_ = 0
        max_val = 0
        for sym in s[::-1]:
            val = sym_val[sym]
            if val < max_val:
                int_ -= val
            else:
                int_ += val
                max_val = val
        return int_
```
I am lucky to get
> Runtime: **120 ms**, faster than **99.54%** of Python3 online submissions for Roman to Integer.

Alternatively, name `max_val` to `prev_val`, which means to value of previous symbol when we traverse `s` reversely. It just happened that `prev_val == max_val` because subtractions are restricted in roman numeral after all.

## Variants

### Left to right
If the next symbol has greater value, substract the current one.

### Replace certain pattern

We can ignore substraction related rules while generating string `roman`, but dealt with those rules afterwards by replacing following patterns:

|---------------------+--------------|
| Replace             | by           |
|---------------------| ------------ |
| DCCCC               | CM           |
| CCCC                | CD           |
| ⋮                    | ⋮            |
| VIIII               | IX           |
| IIII                | IV           |

