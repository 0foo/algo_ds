### Permutations

* This is pretty important in a lot of recursive and dynamic problems
* Different order is a different set in permutation, but is same set in combination

* 2 letter combination sets of ABCDE
    * AB, AC, AD, AE, BC, BD, BE, CD, CE, and DE.


* 2 letter permutation sets of ABCDE
    * AB, BA, AC, CA, AD, DA, AE, EA, BC, CB, BD, DB, BE, EB, CD, DC, CE, EC, DE, ED

* Coin change problem
    * All of these will be some form of finding combinations, not permutations.

* The brute force version of the coin change problem get's all PERMUTATIONS
    * this will have repeating sets with different order


* https://www.techiedelight.com/coin-change-problem-find-total-number-ways-get-denomination-coins/

```python
n = 11
c = [1,2,5]
out = []

def getPermutations(currTotal=0, currArray=None):
    
    if currTotal == n:
        out.append(currArray)
        return
    
    if currTotal > n:
        return

    for j in c:
        
        if currArray == None:
            currArray = []
            
        getPermutations(currTotal + j, currArray + [j])

getPermutations()

print(len(out))  # 218 different permutations
```

```python
n = 5
c = [1,2,3]
out = []

def getPermutations(currTotal, currArray):
    if currTotal == 0:
        out.append(currArray)
    
    if currTotal < 0:
        return

    for coin in c:
        getPermutations(currTotal - coin, currArray + [coin])

getPermutations(5, [])

for i in out:
    print(i)

print(len(out)) # 13
```
