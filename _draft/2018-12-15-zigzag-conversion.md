---
title: "ZigZag Conversion"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/zigzag-conversion/description/)
/
[solution](https://leetcode.com/problems/zigzag-conversion/solution/#approach-1-brute-force-accepted)

## Solution in Python3
```python
        (rowNum * 2 - 2) * i
        (rowNum * 2 - 2) * i +- 1
        (rowNum * 2 - 2) * i +- 2
        (rowNum * 2 - 2) * i +- 3
        ...
        (rowNum * 2 - 2) * i +- rowNum - 1

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
                j = i + cycle_len - 2 * rn
                if (rn != 0 
                    and rn != numRows - 1 
                    and j < len(s)): 
                    zz += s[j]
        return zz

                """
                j = i + cycle_len - 2 * rn
                pivoting next begining
                j = i - rn + cycle_len - rn
                go back to current begining -> next beginning
                j = i + 2 * (numRows - rn - 1)
                pivoting at last row
                """
```
Code credit: [Jedihy](https://github.com/csujedihy/lc-all-solutions/blob/master/214.shortest-palindrome/shortest-palindrome.py)
{: .text-right}

## Variants

### Iterate through `s`
Make a list of strings, one for each row. Append each charater in `s` to proper string. [sample](https://leetcode.com/problems/zigzag-conversion/solution/#approach-1-sort-by-row)

### Others
[Interesting cycle and appending order](https://github.com/csujedihy/lc-all-solutions/blob/master/006.zigzag-conversion/zigzag-conversion.py)
