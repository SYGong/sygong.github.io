---
title: "Letter Combinations of a Phone Number"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)
/
no solution provided

## Solution in Python3
```python
class Solution:
    def letterCombinations(self, digits):
        """
        :type digits: str
        :rtype: List[str]
        """
        letters = [
            '',
            '',
            'abc',
            'def',
            'ghi',
            'jkl',
            'mno',
            'pqrs',
            'tuv',
            'wxyz'
        ]       
        combinations = []
        path = []

        def dfs(digits):
            nonlocal combinations, path
            if digits == '':
                if len(path) > 0:
                    combinations.append(''.join(path))
                return
            for c in letters[int(digits[0])]:
                path.append(c)
                dfs(digits[1:])
                path.pop()
                
        dfs(digits)
        return combinations
```