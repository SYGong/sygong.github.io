---
title: "Longest Substring Without Repeating Characters"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)
/
[solution](https://leetcode.com/problems/longest-substring-without-repeating-characters/solution/#approach-3-sliding-window-optimized)

## Solution in Python3
```python
class Solution:
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        first = 0  # index of current substring
        char_index = {}
        max_len = 0
        for i, c in enumerate(s):
            if c in char_index:
                first = max(char_index[c] + 1, first)
            char_index[c] = i
            max_len = max(i - first + 1, max_len)
        return max_len
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
Actually, this is my first solution. It use less space but there are trade-offs. [another implementation on LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters/solution/#approach-2-sliding-window).

### Remaining length
```diff
        for i, c in enumerate(s):
+           if len(s) - first < max_len: 
+               break
            if c in char_index:
```