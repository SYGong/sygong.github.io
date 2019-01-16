---
title: "Longest Substring Without Repeating Characters"
tags: [LeetCode, Python3]
categories: leetcore
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
            if c in char_index and char_index[c] >= sub_start:
                sub_start = char_index[c] + 1
            else:
                max_len = max(i - sub_start + 1, max_len)
            char_index[c] = i            
        return max_len
```
I am lucky to get
> Runtime: **124 ms**, faster than **90.32%** of Python3 online submissions for Longest Substring Without Repeating Characters.

### Time Complexity
$$O(l)$$, where $$l$$ is the length of `s`.

## Variants

### Remaining length
```diff
            if c in char_index and char_index[c] >= sub_start:
                sub_start = char_index[c] + 1
+               if len(s) - sub_start < max_len:
+                   break
            else:
```
It is a tad faster with
> Runtime: **120 ms**, faster than **94.55%** of Python3 online submissions for Longest Substring Without Repeating Characters.