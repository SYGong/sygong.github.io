---
title: "ZigZag Conversion"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/zigzag-conversion/description/)
/
[solution](https://leetcode.com/problems/zigzag-conversion/solution/#approach-2-visit-by-row)

## Solution in Python3
```python
class Solution:
    def convert(self, s, numRows):
        """
        :type s: str
        :type numRows: int
        :rtype: str
        """
        if numRows == 1:
            return s
        zz = ''
        cycle_len = 2 * numRows - 2
        for rn in range(numRows):
            # rn for row number
            for i in range(rn, len(s), cycle_len):
                zz += s[i]
                if rn != 0 and rn != numRows - 1:
                    j = i + cycle_len - 2 * rn
                    if j < len(s): 
                        zz += s[j]
        return zz
```

## Variants

### Iterate through `s`
Make a list of strings, one for each row. Append each charater in `s` to proper string. [sample1](https://leetcode.com/problems/zigzag-conversion/solution/#approach-1-sort-by-row) [sample2](https://www.geeksforgeeks.org/print-concatenation-of-zig-zag-string-form-in-n-rows/)
