## Handy Equations

* Sum integers 1 to n
    * Also: (x) + ( x + 1 ) + (x + 2)..... or (x) + (x - 1) + (x - 2).....
    * Simplified to `sum of natural integers` : `1 + 2 + 3..+ n` 
    * these both become `n ( n + 1 ) / 2`
    * also (n^2 / 2) + (n / 2)
    * this is a time complexity of n ^ 2 as n gets large, in asymptotic analysis
    * is typically in things like bubble sort where you iterate over the array then move forward one, then re-iterate
  

* Logarithms: don't forget logn2 = N 
    * same as: 2 ^ X = N
    * x = 3
    * typically base 2 is inferred in big O
  
* n + n/2 + n/4 + n + ... + 1: This is roughly 2n
  * this is basically O(n) in big O as the constant cancels out


* N^2/2 is a big O of O(n^2) as the constant cancels


### Factorial
* n =	0	1	2	3	4	5	6	7	8	9	10	11	12	13	14	...
* x = 


### Fibonacci
* n =	0	1	2	3	4	5	6	7	8	9	10	11	12	13	14	...
* x =	0	1	1	2	3	5	8	13	21	34	55	89	144	233	377	...
* fibonacci(6) = 8 
  * 3 + 5 = 8


* Fiboncci extra credit:
  * Using The Golden Ratio to Calculate Fibonacci Numbers
  * Can calculate any Fibonacci Number using the Golden Ratio:

  ```python
  import math
  golden_ratio = 1.618034 # is an irrational number and continues 
  n = 7
  x = ( ( golden_ratio ** n ) - (1 - golden_ratio) ** n  ) /  math.sqrt(5)
  print( int(x) )
  `````

  * Can also calculate a Fibonacci Number by multiplying the previous Fibonacci Number by the Golden Ratio and then rounding 
    * works for numbers above 1
    * Example: 8 × golden_ration = 8 × golden_ratio = 12.94427... = 13 (rounded)


