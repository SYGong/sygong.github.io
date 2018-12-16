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
```

## Variants

### Failure table
Inspired by KPM (Knuth-Morris-Pratt) algorithm. Refer to following links for details
- [KMP solution by LeetCode](https://leetcode.com/problems/shortest-palindrome/solution/#approach-3-kmp-accepted)
- <http://www.personal.kent.edu/~rmuhamma/Algorithms/MyAlgorithms/StringMatch/kuthMP.htm>
- <https://blog.csdn.net/v_july_v/article/details/7041827>
- [Shortest Palindrome by IDeserve](https://www.youtube.com/watch?v=c4akpqTwE5g)
- [Knuth–Morris–Pratt algorithm on Wikipeida](https://en.wikipedia.org/wiki/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm)

```python
class Solution:
    def shortestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        r = s[::-1]
        p = '#'.join([s, r]) # '#' special separater
        f = [0] * len(p) # Failure table

        for i in range(1, len(p)):
            j = f[i - 1]
            while j > 0 and p[i] != p[j]:
                j = f[j - 1]
            if p[i] == l[j]:
                f[i] = j + 1
        
        return ''.join([r[:len(s) - f[-1]], s])
```

### Others
[Two pointers and recursion from LeetCode](https://leetcode.com/problems/shortest-palindrome/solution/#approach-2-two-pointers-and-recursion-accepted)
[GeeksforGeeks](https://www.geeksforgeeks.org/minimum-insertions-to-form-shortest-palindrome/)
