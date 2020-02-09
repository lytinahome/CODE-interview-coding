# Prefix Sum

## How to create a Prefix Sum List

Method #1: Using list comprehension + sum() + list slicing
```
test_list = [3, 4, 1, 7, 9, 1] 
res = [sum(test_list[ : i + 1]) for i in range(len(test_list))] 
```

Method #2: Using accumulate(iterable) method.
```
from itertools import accumulate  
test_list = [3, 4, 1, 7, 9, 1] 
res = list(accumulate(test_list))
```

Method #3: Miminum time complexity
```
test_list = [3, 4, 1, 7, 9, 1]
res = [test_list[0]]
for num in test_list[1:]:
    res.append(res[-1] + num)
```


### Puzzles in leetcode
|  |  |
|--|--|
| 2 | 41. * Maximum Subarray |
