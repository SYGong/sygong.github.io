---
title: "Multiply Strings"
tags: [LeetCode, Python3]
categories: leetcore
---

## From LeetCode
[problem description](https://leetcode.com/problems/multiply-strings/description/)
/
no solution provided

## Solution in Python3
```python
class Solution(object):
    def multiply(self, num1, num2):
        """
        :type num1: str
        :type num2: str
        :rtype: str
        """
        l1, l2 = len(num1), len(num2)
        lp = l1 + l2   
        product = [0] * lp  # product[0] for possible carry
        for i in range(l1):
            for j in range(l2):
                product[i + j + 1] += int(num1[i]) * int(num2[j])
        for i in reversed(range(lp)):    
            product[i - 1] += product[i] // 10
            product[i] %= 10
        while len(product) > 1 and product[0] == 0:
            product.pop(0)
        return "".join(map(str, product))
```

### Time Complexity
$$O(l_1 l_2)$$, where $$l_1$$ and $$l_2$$ are the length of `num1` and `num2`, respectively.

## Variants

### `return str(int(num1) * int(num2))`
Use `int` or `eval` is cheating, but LeetCode will not prevent you get following results
 
|---------------------+--------------+------------|
| Solution            | Runtime (ms) | Beat %     |
|---------------------| -----------: | ---------: |
| our complicated one | 164          | 52.92      |
| `eval()`            | 100          | 60.95      |
| `int()`             | **40**       | **100.00** |

It beats everyone.