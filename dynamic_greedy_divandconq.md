### Greedy
* uses the local maxima/minima for the current recursive call/iteration
* ex:
    * smallest denomiation of change
        * will grab largest possible coin at each recursive iteration that's < demonimation
    * find the smallest number of n in array that equal a sum
        * will grab the largest item from the c array each iteration/recursive call
    * also works for finding the largest number of n in array that equal a sum (use min() instead of max())

```python
n = 11
c = [1,2,5]
total = 0
x = 0

while total <= n:
    cur_max = max(c)

    if total + cur_max < n:
        total += cur_max
    else:
        c.remove(cur_max)
        
    if total == n:
        return x

return -1
```

### Divide and Conquor
* recursively break apart and solve smaller problems to solve the whole
* differs from dynamic programming in that there's no overlapping subproblems
    * every iteration has a completely separate set of data to operate on and the data sets never overlap in future recursive calls/iterations
    * every iteration splits data in two and all the future calls and subcalls never touch each others data
* ex:
    * binary search
    * binary partitioning
        * sorts that use parititioning and recombination use a binary partition: mergesort, quicksort, etc


### Dynamic Programming
* basically taking a recursive problem and adding memoization or tabulation to stop duplicate calcuation of overlapping subproblems
* only useful if there's overlapping sub-problems
* Dynamic has overlapping problems!
    *  it works around this with memoization and tabulation
    *  vs. divide and conqor which has clean separation of data in each division! 
* a tabulation implementation is always iterative.
* a memoization implementation is always recursive
    * memoization or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again
* memoization vs tabulation
   * memoization is still subject to stack overflows
   * tabulation is usually faster as there's no recursion overhead
   * If only some of the subproblems need to be solved for the original problem to be solved, then memoization is preferrable since only the needed subproblems are solved
   * Recursion with memoization is better whenever the state space is sparse -- in other words, if you don't actually need to solve all smaller subproblems but only some of them.
   * Iterative solutions are better whenever the state space is dense and regular. If you need to compute the solutions to all the subproblems anyway, you may as well do it without all the function calling overhead.
   * An additional advantage of the iterative approach is that you are often able to save memory by forgetting the solutions to subproblems you won't need in the future. E.g., if you only need row k of the table to compute row k+1, there is no need to remember row k-1 anymore.


### Factorial Brute Force
```python
def factorial(n):
    if n <= 0:
        return 1
    if n == 1:
        return 1
    return n * factorial(n-1)
    
out = factorial(5)
print(out)
```


### Factorial Tabulation
``` python
n = 5
# Tabulated version to find factorial x.

tab = [None] * 6
tab[0] = 1

for i in range(1, n + 1):
    tab[i] = tab[i-1] * i
    print(tab)

```

```python
[1, 1, None, None, None, None]
[1, 1, 2, None, None, None]
[1, 1, 2, 6, None, None]
[1, 1, 2, 6, 24, None]
[1, 1, 2, 6, 24, 120]

```

### Factorial Memoization
* note: this is useless purely inside the function, as it only calls each recursive function once, but if you use this function numerous times in a program is timesaver

```python
n = 5
memo = [None] * (n + 1)
memo[0] = 1
# return fact n!
def factorial_memoization(n):
    if memo[n] is not None:
        return memo[n]
    memo[n] = n * factorial_memoization(n - 1)
    print(memo)
    return memo[n]
out = factorial_memoization(n)
print(out)
```

* the results of the memoization
```python
[1, 1, None, None, None, None]
[1, 1, 2, None, None, None]
[1, 1, 2, 6, None, None]
[1, 1, 2, 6, 24, None]
[1, 1, 2, 6, 24, 120]
120
```


### Fibonacci Brute Force
* see fibonacci info in hand_equations.md

```python
def fibonacci_brute_force(x):
    if x == 0:
        return 0
    if x == 1 or x == 2:
        return 1
    
    return fibonacci(x - 1) + fibonacci(x - 2)
```

### Fibonacci Tabulation

```python

def fibonacci_tabulation(n){
  if n == 0 or n == 1 or n== 2:
      return 1

  tab = [0,1,1]

  for i in range(3, n):
    fibNums[i] = fibNums[i-1] + fibNums[i - 2]
  
  return fibNums[n]

```

### Fibonacci Memoization

```python
n = 5
memo = [None] * (n + 1)
memo[0] = 0
memo[1] = 1
memo[2] = 2

def fibonacci_memoization(x):
    if memo[x] is None:
        memo[x] = fibonacci_memoization(x-1) + fibonacci_memoization(x-2)
    return memo[x]

out = fibonacci_memoization(n)
print(out)

```










