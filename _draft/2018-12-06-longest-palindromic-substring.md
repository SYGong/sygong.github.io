---
title: "Longest Palindromic Substring"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/longest-palindromic-substring/description/)
/
[solution]()

## Solution in Python3
```python
class Solution:
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        sub_first, sub_last, max_len = 0, 0, 0
        for core in range(len(s)):
            for arm in range(min(core, len(s) - 1 - core)):
                if s[core + arm] == s[core - arm]:
                    if 1 + arm * 2 > sub_last - sub_first:
                        sub_first = core - arm
                        sub_last = core + arm
                        max_len = sub_last - sub_first + 1
                else:                    
                    break
        
        for core in range(len(s) - 1):
            for arm in range(1, min(core + 1, len(s) - 1 - core)):
                if s[core - arm + 1] == s[core + arm]:
                    if arm * 2 > max_len:
                        sub_first = core - arm + 1
                        sub_last = core + arm
                        max_len = sub_last - sub_first + 1
                else:                    
                    break
        return s[sub_first : sub_last + 1]
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