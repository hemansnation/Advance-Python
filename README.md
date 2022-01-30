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
def fibo(n):
    if n == 0 or n == 1:
        return n
    
    else:
        return fibo(n - 1) + fibo(n - 2) 

```
