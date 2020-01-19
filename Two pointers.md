# Two pointers

## -> -> two pointers



|  | **Fast & slow pointers** |
|--|--|
| 1 | 228. Middle of Linked List |

|  | **Sliding Windows** |
|--|--|
| 1 | 604. Window Sum |
|  | 360. Sliding Window Median |
|  | 362. Sliding Window Maximum |
|  | 1375. Substring With At Least K Distinct Characters |

|  | **Remove Duplicate** |
|--|--|
|  | 521. Remove Duplicate Numbers in Array |

|  | **Two Difference** |
|--|--|
|  | 610. Two Sum - Difference equals to target |

|  | **Linked List Cycle** |
|--|--|
|  | 102. Linked List Cycle |
|  | 103. Linked List Cycle II |
|  | 380. Intersection of Two Linked Lists |
|  | 547. Intersection of Two Arrays |


|  |  **Miscellaneous** |
|--|--|
|  | 539. Move Zeroes |



## -> <- two pointers: time complexity $O(n)$.

-  Reverse:

   - 三步翻转法
   - Valid palindrome
   
```
"""
@param s: a list of characters
"""
def reverse(s):
    left, right = 0, len(s)-1
    while left < right:
        s[left], s[right] = s[right], s[left]
        left += 1
        right -= 1
```

-  Two sum: 
```
def twoSum(numbers, target):
    hash_set = set()
    
    for i in range(len(numbers)):
        if target-numbers[i] in hash_set:
            return (numbers[i], target-numbers[i])
        hash_set.add(numbers[i])

    return None
 ```
 
 ```
 class Solution:
    def twoSum(self, numbers, target):
        numbers.sort()

        L, R = 0, len(numbers)-1
        while L < R:
            if numbers[L]+numbers[R] == target:
                return (numbers[L], numbers[R])
            if numbers[L]+numbers[R] < target:
                L += 1
            else:
                R -= 1
        return None
  ```
 


-  Partition

```
while left <= right:
    while left <= right and nums[left] should be in the left side:
        left += 1
    while left <= right and nums[right] should be in the right side:
        right += 1
    
    if left <= right:
        nums[left], nums[right] = nums[right], nums[left]
        left += 1
        right += 1
```
Note the difference with Quick Sort.




|  |  **Reverse**|
|--|--|
|  | 415. Valid Palindrome |
|  | 891. Valid Palindrome II |
|  | 39. Recover Rotated Sorted Array | 

|  |  **Two Sum**|
|--|--|
| 1 | 56. Two Sum |
|  | 608. Two Sum II - Input array is sorted |
| 1 | 607. Two Sum III - Data structure design|
|  | 587. Two Sum - Unique pairs | 
| 1 | 609. Two Sum - Less than or equal to target |
|  | 443. Two Sum - Greater than target |
| 2 | 533. Two Sum - Closest to target|
|  | 610. Two Sum - Difference equals to target |
|  | 57. 3Sum |
| 1 | 59. 3Sum Closest |
|  | 58. 4Sum |
|  | 382. Triangle Count |


|  |  **Partition** |
|--|--|
|  | 31. Partition Array |
|  | 373. Partition Array by odd and even |
|  | 144. Interleaving Positive and Negative Numbers |
|  | 49. Sort Letters by Case |
|  | 5. kth Largest Element |
|  | 461. Kth Smallest Numbers in Unsorted  Array |

|  | **three pointers** |
|--|--|
|  | 148. Sort Colors |
|  | 143. Sort Colors II |




## <- -> two pointers

Longest palindromic substring

Find K closest elements

## Miscellaneous

|  |  **Miscellaneous** |
|--|--|
|  | 894. Pancake Sorting | 

