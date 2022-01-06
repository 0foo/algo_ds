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