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
        zigzag = ''
        cycle_len = 2 * numRows - 2
        for r in range(numRows):
            for i in range(r, len(s), cycle_len):                
                # For each cycle,
                # i is index of first character in row r and
                # j is index of second character in row r.
                
                zigzag += s[i]
                if r != 0 and r != numRows - 1:
                    j = i + cycle_len - 2 * r
                    if j < len(s):
                        zigzag += s[j]
        return zigzag
```

## Variants

### Iterate through `s`
Make a list of strings, one for each row. Append each charater in `s` to proper string. [sample1](https://leetcode.com/problems/zigzag-conversion/solution/#approach-1-sort-by-row) [sample2](https://www.geeksforgeeks.org/print-concatenation-of-zig-zag-string-form-in-n-rows/)
