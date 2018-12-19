---
title: "Integer to Roman"
tags: [LeetCode, Python3]
categories: LeetCode
mathjax: True
---

## From LeetCode
[problem description](https://leetcode.com/problems/integer-to-roman/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def intToRoman(self, num):
        """
        :type num: int
        :rtype: str
        """
        val_sym = [(1000, "M"),
                   (900, "CM"),
                   (500, "D"),
                   (400, "CD"),
                   (100, "C"),
                   (90, "XC"),
                   (50, "L"),
                   (40, "XL"),
                   (10, "X"),
                   (9, "IX"),
                   (5, "V"),
                   (4, "IV"),
                   (1, "I")]
        roman = ''
        for val, sym in val_sym:
            if num == 0:
                break
            n_sym = num // val
            roman += sym * n_sym
            num %= val
        return roman
```
I am lucky to get 
> Runtime: **112 ms**, faster than **99.63%** of Python3 online submissions for Integer to Roman.

## Variants

### Decimal `4` and `9`
Because roman numeral has good relationship with decimal numbers, we can iterate through each digit in decimal number, map digit `4` or `9` to roman numeral in [many ways](https://www.geeksforgeeks.org/converting-decimal-number-lying-between-1-to-3999-to-roman-numerals/). Inspired by those approaches, we can get our `val_sym` computed instead of hard-coded.

### Replace certain pattern

We can ignore substraction related rules while generating `roman`, but dealt with those rules afterwards by replacing following patterns:

|---------------------+--------------|
| Replace             | by           |
|---------------------| ------------ |
| DCCCC               | CM           |
| CCCC                | CD           |
| ⋮                    | ⋮            |
| VIIII               | IX           |
| IIII                | IV           |

