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
        sub_start = 0
        char_index = {}
        max_len = 0
        for i, c in enumerate(s):
            if c in char_index:
                sub_start = max(char_index[c] + 1, sub_start)
            char_index[c] = i
            max_len = max(i - sub_start + 1, max_len)
        return max_len
```

### Time Complexity
$$O(l)$$, where $$l$$ is the length of `s`.

## Variants

### Just maintain `char_index` for current substring
```diff
            if c in char_index:
+               for j in range(sub_start, char_index[c]):
+                   del char_index[s[j]]
-               sub_start = max(char_index[c] + 1, sub_start)
+               sub_start = char_index[c] + 1
            char_index[c] = i            
```
Actually, this is my first solution. It use less space but there are trade-offs. [another implementation on LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters/solution/#approach-2-sliding-window)

### Remaining length
```diff
        for i, c in enumerate(s):
+           if len(s) - sub_start < max_len: 
+               break
            if c in char_index:
```