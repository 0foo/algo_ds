### Greedy
* uses the local maxima
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
* ex:
    * binary search
    * sorts that use parititioning and recombination: mergesort, quicksort, etc

### Dynamic
* Recursively break apart and solve smaller problems to solve the whole 
* Dynamic has overlapping problems!
    *  it works around this with memoization and tabulation
    *  vs. divide and conqor which has clean separation of data in each division! 




### Coin change problem 1
* find the MINIMUM NUMBER of coins to use to make a number: n, out of array of coins: d, 
```python

INF = 100000
#k is number of denominations of the coin or length of d
def coin_change(d, n):
  M = [0]*(n+1)

  # iterate every number up to n
  for current_n in range(1, n+1):
    
    minimum = INF
    #iterate every coin
    for coin_value in d:

      if(coin_value <= current_n):
        prev_n = current_n - coin_value
        prev_value = M[prev_n]
        minimum = min(minimum, 1 + prev_value)
        
    M[current_n] = minimum
    
  return M[current_n]

## Run 
d = [1, 2] # coins
n = 5 # number to make 
print(coin_change(d, n)) 
```




### Coin change problem 2
* find HOW MANY WAYS that coins can be used to make a number: n, out of array of coins: d,  
    * this is a COMBINATION problem, different order still the same set
* https://leetcode.com/problems/coin-change-2/solution/


* Brute Force
    * Note: This has a lot of repitition during recursion. 
        * for example:  5,5,1   will be repeated 3 times: 5,5,1 and  5,1,5 and 1,5,5 
    * The "seen" array prevents it from being counted, at huge time complexity cost,  but the recursion still happens

```python

n = 11
c = [1,2,5]
total = 0
x = 0
seen = set()

def getNumberOfCombinations(currTotal=0, currArray = []):
    if currTotal == n and currArray.sort() not in seen:
        x += 1
        seen.add(currArray)
        return
    
    if currTotal > n:
        return

    for j in c:
        getSmallestQuantity(currTotal + j, currArray.append(j))
return x

```




```python

```