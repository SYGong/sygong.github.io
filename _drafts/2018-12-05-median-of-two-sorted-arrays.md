---
title: "Longest Substring Without Repeating Characters"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems//median-of-two-sorted-arrays/description/)
/
[solution](https://leetcode.com/problems//median-of-two-sorted-arrays/solution/)

## Solution in Python3
```python
class Solution:
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        shorter, longer = sorted((nums1, nums2), key=len)
        s_len, l_len =  len(shorter), len(longer)
        half_len = (s_len + l_len + 1) // 2
        # j = l_len // 2 - (i - s_len // 2) =  
        i_min, i_max = 0, s_len
        while i_min < i_max:
            i = (i_min + i_max) // 2
            j = half_len - i
            if i > 0 and shorter[i - 1] > longer[j]:
                i_max -= 1
            elif i < m and longer[j - 1] > shorter[i]:
                i_min += 1
            else:
                i_min = i + 1
        i = i_min
        nextfew = sorted(a[i:i+2] + b[after-i:after-i+2])
        return (nextfew[0] + nextfew[1 - (m+n)%2]) / 2.0
```

## Variants

### Just maintain `char_index` for current substring
```diff
            if c in char_index:
+               for j in range(first, char_index[c]):
+                   del char_index[s[j]]
-               first = max(char_index[c] + 1, first)
+               first = char_index[c] + 1
            char_index[c] = i            
```
Actually, this is my first solution. It use less space but there are trade-offs. [There is another implementation on LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters/solution/#approach-2-sliding-window).

### Remaining length
```diff
        for i, c in enumerate(s):
+           if len(s) - first < max_len: 
+               break
            if c in char_index:
```