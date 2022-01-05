### Combinations

* Super common questions
* Base/Foundation for dynamic programming

* find number of combinations 
    * how many unique sets can be formed from superset of [a,b,c]
* find number of sets of size x 
    * ex: how many sets of 3 can be formed from the superset of [a,b,c]
* find number of sets that equal a certain sum
    * ex: how many sets equal the number 5 out of the superset [1,2,3]
* find minimum/maximum set size that equals a sum
    * ex: what is the smallest/largest set that equals 7 out of superset [1,2,3]


* Two types of combinations
    1. Without repetition
        * ` [], ['a'], ['b'], ['c'], ['c', 'b'], ['c', 'a'], ['b', 'a'], ['c', 'b', 'a'] `
    2. With repetition
        * ` [], ['a'], ['b'], ['c'], ['c', 'b'], ['c', 'a'], ['b', 'a'], ['c', 'b', 'a'] `
        * ` ['a', 'a'], ['b', 'b'], ['c', 'c'], ['a', 'a', 'a']...etc.`
        * Note: still differ's from permutation in that `['c', 'b']` is still the same as `['b', 'c']`

#### Without repetition
* decent video tutorial here:
    * https://www.youtube.com/watch?v=NA2Oj9xqaZQ

* Note: the key is the last return statement
    * it allows every recursive call to build upon the previous


```python
superset = ['a', 'b', 'c']

def combinations_no_reps(elements):
    if len(elements) == 0:
        return [[]]

    first = elements[0]
    rest = elements[1:]

    no_first = combinations_no_reps(rest)
    with_first = []

    for i in no_first:
        current = i + [first]
        with_first.append(current)
    
    return no_first + with_first

out = combinations_no_reps(superset)
print(out)
```


### With repetition
* This is used in the coin change problem









* include/exclude method

```python
    # S = list of coins
    # target = number trying to find combinations to reach
    # n = current coin\
  # Case 1. Include current coin `S[n]` in solution and recur
    # with remaining change `target-S[n]` with the same number of coins
    incl = count(S, n, target - S[n])

 # Case 2. Exclude current coin `S[n]` from solution and recur
    # for remaining coins `n-1`
    excl = count(S, n - 1, target)
 
    # return total ways by including or excluding current coin
    return incl + excl
```





```python
n = 11
c = [1,2,5]
out = []

def getCombinations():


```