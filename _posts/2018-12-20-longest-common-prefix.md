---
title: "Roman to Integer"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/longest-common-prefix/)
/
[solution]

## Solution in Python3
```python
class Solution:
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if len(strs) == 0:
            return ''
        for i in range(len(strs[0])):
            for j in range(1, len(strs)):
                if (len(strs[j]) <= i 
                    or strs[0][i] != strs[j][i]):
                    return strs[0][:i]
        return strs[0]
```

## Variants

### Word by word
[LeetCode][solution] call it horizontal scanning. [another sample on GeeksforGeeks](https://www.geeksforgeeks.org/longest-common-prefix-using-word-by-word-matching/)

### Trie
Get a trie. [sample](https://www.geeksforgeeks.org/longest-common-prefix-using-trie/)

### Binary search for prefix length
This is more time comsuming, unless we can compare two string as fast as two characters. [sample](https://www.geeksforgeeks.org/longest-common-prefix-using-binary-search/)

The length of shortest string will be the maximum length of common prefix. 
{: .notice}

[solution]: (https://leetcode.com/problems/longest-common-prefix/solution/)