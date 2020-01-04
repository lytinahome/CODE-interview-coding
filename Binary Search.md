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
* general template
* xxoo
* keep the half
* binary the answer


