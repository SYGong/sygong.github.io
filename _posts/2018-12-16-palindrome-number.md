---
title: "Palindrome Number"
tags: [LeetCode, Python3]
categories: leetcore
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
I got
> Runtime: **440 ms**, faster than **79.39%** of Python3 online submissions for Palindrome Number.

### Time Complexity
$$O(n)$$, where $$n$$ is the number of digits.

## Variants

### Without `math.log10()`
Count iterations of `x //= 10` until `x == 0`. [sample](https://github.com/qiyuangong/leetcode/blob/master/python/009_Palindrome_Number.py)

### Without compute # of digits
```diff
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
        x_str = str(x)
        for i in range(len(x_str) // 2):
            if x_str[i] != x_str[-i - 1]:
                return False
        return True
```
LeetCode says *"... this would require extra **non-constant** space for creating the string which is not allowed by the problem description."* 

Well, I don't buy it, because LeetCode keeps gaslighting us with integer overflow issues including this problem ([LeetCode's solution][solution] second intuition) and many others ([atoi], [reverse-integer] and etc.). If an integer limited to, say 32 bits, then $$O(2^{32}) = O(1)$$ and I don't see why its string needs **non-constant** space. 

I submit this solution and get
> Runtime: **288 ms**, faster than **99.11%** of Python3 online submissions for Palindrome Number.

Faster than most solutions above.

### Recursion
The [sample](https://www.geeksforgeeks.org/check-if-a-number-is-palindrome/) is a little bit tricky.

[reverse-integer]: https://leetcode.com/problems/reverse-integer/description/
[atoi]: https://leetcode.com/problems/string-to-integer-atoi/description/
[solution]: (https://leetcode.com/problems/palindrome-number/solution/)