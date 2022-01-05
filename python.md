### List slicing
* x[0:2] is the first two items: index 0 and index 1; the end bound is not inclusive; shortcut x[:2]
* x[2:0] skips the first two items == x[2: end of array]
* x[:-1] skips the LAST item; == x[0:-1] == x[ 0:last_item - 1]
* x[-1] IS the last item; negative indexing; == x[last item - 1]
* x[include:exclude]



### Make a list predefined with values and size
* new_list = [None] * 10
* creates list of size 10 with all values as None



* basic notation
    * a[start:stop]  # items start through stop-1
    * a[start:]      # items start through the rest of the array
    * a[:stop]       # items from the beginning through stop-1
    * a[:]           # a copy of the whole array



### all()/any()
all:checks if all elements are True/ any:checks if any elements are True

x = [None, None]
x = [v == None for v in x]
print(all(x))


### min()/max()
print(min(1,2)) # 1

* works with list as well
    * max([1,2,3])

### character checks
i.isalpha() = return True if letter
i.isdigit() = returns True if digit
i.lower() = returns lower case


### remove from list
del     O(n - i)  index removal
pop     O(n - i)  index removal
remove  O(n)      value removal

using a list as queue: has to shift array every pop/del from the beginning. O(n) operation.
x = []
x.append("somevalue")
1. y = x.pop(0)
2. y = x[0]
    del test_list[0]


### python queue
most efficient:

from collections import deque
queue.append(1)
x = queue.popleft()


### remove multiple items from list
 iterate the positions in reverse order, 
 so removing an item doesn't shift the positions of the remaining (earlier) list items.

solution 1:
idx = [n for n, x in enumerate(my_list) if x == 0]
for i in reversed(idx):
    my_list.pop(i)

solution 2:
list = [0, 0, 0, 1, 1, 0 ,0, 1, 0]

for elem in reversed(list):
    if elem == 0:
        list.remove(elem)


### sorting
my_list.sort() # n log n


### iterate
for k,v in enumerate(my_list):
for k,v in my_dict.items():


### combining/appending

x.append() # appends in place
[1] + [2]  # creates a new array and leaves the other two alone
x[4:7] # creates a new array and leaves original alone



reference:
https://stackoverflow.com/questions/58962005/delete-elements-from-list-in-python-and-avoid-shifting