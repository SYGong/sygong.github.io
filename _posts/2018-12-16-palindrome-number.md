---
title: "Palindrome Number"
tags: [LeetCode, Python3]
categories: LeetCode
mathjax: True
---

## From LeetCode
[problem description](https://leetcode.com/problems/palindrome-number/description/)
/
[solution]

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

### Without `math.log10()`
Count number of `x //= 10` until `x == 0`. [sample](https://github.com/qiyuangong/leetcode/blob/master/python/009_Palindrome_Number.py)

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
**Note:** `x == rev_x // 10` is `True` **if and only if** original `x` is palindrome with odd number of digits.
{: .notice}

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
LeetCode says *"... this would require extra **non-constant** space for creating the string which is not allowed by the problem description."* Well, I don't buy it, because LeetCode keeps gaslighting us with integer overflow issues including this problem ([LeetCode's solution][solution] second intuition) and many others ([[1]], [[2]] and etc.). Hey, $$O(2^{31}) = O(1)$$ and it is still a **constant**, right? 

So I submit this solution anyway and it beats 70.27%, inluding some solutions above.

### Recursion
The [sample](https://www.geeksforgeeks.org/check-if-a-number-is-palindrome/) is a little bit tricky.

[1]: https://leetcode.com/problems/reverse-integer/description/
[2]: https://leetcode.com/problems/string-to-integer-atoi/description/
[solution]: (https://leetcode.com/problems/palindrome-number/solution/)