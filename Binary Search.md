# Binary Sreach

## General Template
```
start, end = 0, len(nums) - 1
while start + 1 < end:
    mid = (start + end)//2
    if nums[mid] == target:
        return mid
    elif nums[mid] < target:
        start = mid
    else:
        end = mid
        
if nums[start] == target:
    return start
if nums[end] == target:
    return end
return -1

```
### Question: what is the time complexity of binary search

### Qeustion: four ways to apply binary search

|  | **general template** |
|--|--|
|  | 457. calssical binary search|
|  | 14. first position of target|
|  | 458. last position of target|
|  | 447. search in a big sorted array|
|  | 460. find k closest elements|
|  | 61. search for a range|
|  | 600. smallest rectangle enclosing black pixels|


|  | **xxoo** |
|--|--|
|  | 585. maximum number in mountain sequence|
|  | 159. find minimum in rotated sorted array|

|  | **discard the half** |
|--|--|
|  | 62. search in rotated sorted array|
| 1 | 75. find the peak element|

|  | **binary the answer** |
|--|--|
|  | 65. median of two sorted arrays|
|  | 931. median of k sorted arrays|

|  | **trinary search** |
|--|--|
|  |   |

|  | **exponantial backoff** |
|--|--|
|  | 428. pow(x, n)|
|  | 140. fast power|
| 1 | 74. first bad version|
|  | 141. sqrt(x)|
|  | 586. sqrt(x) II|



### Question: applications in binary search
* find target
* exponential backoff

### Question: what if there is duplicates in the array
the time complexity will be $O(n)$ instead of $O(log n)$ and it is unavoidable.

