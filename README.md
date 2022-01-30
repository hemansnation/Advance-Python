# Advance-Python
Advance Python Programming Logic Building

## Recursion

- Recursion is a powerful technique that can be used to solve complex and long tail problems.

- Recursion is essentially based on divide and conquer technique where we divide the problem into different subproblems, solve each subproblem recursively, and combine the results to form the final solution.

- Most recursive problems can be solved iteratively with for and while loops. While recursion might make use of few codes than iterative approach, the iterative approach might take less computation time and space. There a fair trade-off between recursion and iterative approach.

### Example Interview Questions

1. Return Multiplication of 2 numbers without using * 

``` python
def multiply(a, b):

    s = 0
    while b > 0:
        s += a
        b -= 1
        
    return s
```

Recursive Approach

```python
def multiply(a, b):
    if b == 1:
        return a
    else:
        return a  + multiply(a, b - 1)

```

2. Factorial of a number

``` python
def factorial(n):
    if n == 1 or n == 0:
        return 1
    
    else:
        return n * factorial(n - 1)

```

3. Fibonacii Series

``` python
def fibonacii(n):
    if n == 0 or n == 1:
        return n
    
    else:
        return fibonacii(n - 1) + fibonacii(n - 2) 

```

- Fibonacci series of large numbers are hard to compute. Take for example: Computing fibonacii(120) gives 8,670,007,398,507,948,658,051,921 and if we assume each recursive call takes a nanosecond, it would take 250,000 years to finish. The reason why it takes lots of time to compute fibonacci series is that there are multiple similar recursive calls that are computed at every step.


## Dynamic Programming

- Dynamic programming is an efficient technique that is used to solve problems that have overlapping problems (subproblems that contains other subproblems).
- Dynamic programming solves each subproblem once, save or cache the results, and use the results later rather than recomputing the subproblem. Storing the results of all possible subproblems in a systematic way reduce the time and space required to reach to the optimal solution. The work is merely minimized.
- Dynamic programming is used to solve optimization problems - Optimization problems are problems whose solutions maximizes or minimizes some function. Example of optimization: gradient descent that minimize the loss function.
- The process of storing the computed results of subproblems and using them later wherever possible is called memoization.


Lets solve the fibonacii series with Dynamic Programming.

The only thing we do is to store the results of the similar recursive calls and reuse them everytime we face them rather than recomputing twice or thirdth or fourth.

```python
def fibonacii(n, memo = {}):
    if n == 1 or n == 0:
        return n
    
    if n > 1:
        if n in memo:
            return memo[n]
        else:
            result = fibonacii(n - 1, memo) + fibonacii(n - 2, memo)
            memo[n] = result
            return result

```

The runtime of fibonacii(n) is O(n) since we are caching the results and there are only n values to pass to fibonacii(n). Looking the value in a dictionary takes O(1) constant time, so we don't count that. This also much better than O(2^n) of normal recursive function.
