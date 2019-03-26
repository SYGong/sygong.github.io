---
title: "Linearity"
tags: []
categories: []
---

## Problem
Suppose that an intermixed sequence of (stack) push and pop operations are performed. The pushes push the integers 0 through 9 in order; the pops print out the return value. Which of the following sequence(s) could not occur? [Possible origin](https://www.cs.princeton.edu/courses/archive/fall14/cos126/precepts/StackQueueEx.pdf_

A. 4 3 2 1 0 9 8 7 6 5  
B. 4 6 8 7 5 3 2 9 0 1  
C. 2 5 6 7 4 8 9 3 1 0  
D. 4 3 2 1 0 5 6 7 8 9  
E. 1 2 3 4 5 6 9 8 7 0  
F. 0 4 6 5 3 8 1 7 2 9  
G. 1 4 7 9 8 6 5 3 0 2  
H. 2 1 4 3 6 5 8 7 9 0  

## Answer
B, F, and G

### Short explaination
B: 0 is under 1, so 0 can not be popped before 1.
F: 1 can't be popped before 7 and 2
G: 0 can't be popped before 2

### Algorithm
It turns out, we can write algorithm to check a sequence
```python
def good_pops(seq):
    stack = []
    for i in range(10):
        stack.append(i)
        while len(stack) > 0 and stack[-1] == seq[j]:
            stack.pop()
            j += 1
    return len(stack) == 0
```

#### Time complexity
$$O(N)$$, where $$N$$ is the number of elements to be pushed in the stack. Although there is a nested `while` loop, `pop()` will be executed equal or less than $$N$$ times.
