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
        else x % 10 == 0:
            return False
        rev_x = 0
        while x > rev_x:
            rev_x *= 10 
            rev_x += x % 10
            x //= 10
        return x == rev_x or x == rev_x // 10
```
I got
> Runtime: **440 ms**, faster than **79.39%** of Python3 online submissions for Palindrome Number.

Many conditions need to consider. Roughtly speaking, the while loop will cut the number into halves and reverse the second half. I say roughtly because this will only happen when `x` has even number of digits and left most digit is less than or equal to right most digit, e.g. `x = 1234` will results `12` and `43` but if `x =  4321` will then be `123` and `4` and you need be careful. If Then you need to be careful about what do you have for 

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
This avoid `math.log10` function and has better performance 
> Runtime: **276 ms**, faster than **99.18%** of Python3 online submissions for Palindrome Number.

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

Faster than most solutions above and I feel no guilty.

### Recursion
The [sample](https://www.geeksforgeeks.org/check-if-a-number-is-palindrome/) is a little bit tricky.

[reverse-integer]: https://leetcode.com/problems/reverse-integer/description/
[atoi]: https://leetcode.com/problems/string-to-integer-atoi/description/
[solution]: (https://leetcode.com/problems/palindrome-number/solution/)