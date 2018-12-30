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
        num_char = [
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
        letters = []

        def dfs(digits):
            nonlocal combinations, letters
            if digits == '':
                if letters:
                    combinations.append(''.join(letters))
                return
            for c in num_char[int(digits[0])]:
                letters.append(c)
                dfs(digits[1:])
                letters.pop()
                
        dfs(digits)
        return combinations
```