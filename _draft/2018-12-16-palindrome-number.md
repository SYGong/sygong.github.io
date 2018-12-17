---
title: "Palindrome Number"
tags: [LeetCode, Python3]
categories: LeetCode
---

## From LeetCode
[problem description](https://leetcode.com/problems/palindrome-number/description/)
/
[solution](https://leetcode.com/problems/palindrome-number/solution/)

## Solution in Python3
```python
import math

class Solution:
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x == 0:
            return True
        if x < 0 or x % 10 == 0:
            return False
        digits = int(math.log10(x)) + 1
        rev_x = 0
        for d in range(digits // 2):
            rev_x *= 10 
            rev_x += x % 10
            x //= 10
        if digits % 2 == 1:
            x //= 10
        return x == rev_x
```

## Variants

### Without compute # of digits
```diff
        if x < 0 or x % 10 == 0:
            return False
-       digits = int(math.log10(x)) + 1
        rev_x = 0
-       for d in range(digits // 2):
+       while x > rev_x:
            rev_x *= 10 
            rev_x += x % 10
            x //= 10
-       if digits % 2 == 1:
-           x //= 10
-       return x == rev_x
+       return x == rev_x or x == rev_x // 10
```
In last line `x == rev_x // 10` could noly be `True` when original `x` is a palindrome with odd number of digits. [LeetCode's solution](https://leetcode.com/problems/palindrome-number/solution/#approach-1-revert-half-of-the-number) explianed why it is necessary but do not explain why this is sufficeint. However we also want to make sure it will not be `True` given any non-palindromic `x`. It won't, because if `x == rev_x // 10` is `True`, number of digits must be odd and the rest of 


### Convert to string
```python
class Solution:
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if x == 0:
            return True
        if x < 0 or x % 10 == 0:
            return False
        x_str = str(x)
        for i in range(len(x_str) // 2):
            if x_str[i] != x_str[-i - 1]:
                return False
        return True
```
