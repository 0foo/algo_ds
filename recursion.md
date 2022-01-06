### Recursion

* useful when don't know how many loops will need.
    * example: calculating combination to equal a sum from an array of different numbers
    * given an array of [1,2,3] find how many combinations equal 9.
        * can't use a loop because will need 3 nested loops for the 3 + 3 + 3, and 5 nested loops for 2+2+2+2+1
        

* different types of recursion

```python
def factorial(n):
    if n <=0:
        return 0
        
    if n <= 1:
        return 1
        
    return factorial(n-2) + factorial(n-1)
```

```python
function factorial(x)
    if x is 0                   
        return 1
    return x * factorial(x-1)     
```





### Backtracking
* Backtracking Runtime
    * The way I like to think about the runtime of backtracking algorithms is O(b^d), where b is the branching factor and d is the maximum depth of recursion.
    * Backtracking is characterized by a number of decisions b that can be made at each level of recursion. If you visualize the recursion tree, this is the number of children each internal node has. You can also think of b as standing for "base", which can help you remember that b is the base of the exponential.
    * If we can make b decisions at each level of recursion, and we expand the recursion tree to d levels (ie: each path has a length of d), then we get b^d nodes. 
    * Since backtracking is exhaustive and must visit each one of these nodes, the runtime is O(b^d).
    * Note: if b and d aren't constant use the maximum of these