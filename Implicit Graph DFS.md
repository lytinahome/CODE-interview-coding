# Implicit Graph DFS



|  | **Combination** |
|--|--|
| 3 | 17. Subsets |
|  | 18. Subsets II |
|  | 426. Restore IP Address |
|  | 427. Generate Parentheses |
|  | 152. Combinations |


|  | **Permutation** |
|--|--|
|  | 15. Permutation |
|  | 16. Permutation II |
|  | 52. Next Permutation |
|  | 53. Next Permutation II |
|  | 10. String Permutation II |

## Example: find all combinations in a set.
Solution 1:
```
class Solution:
    
    def search(self, nums, S, index):
        if index == len(nums):
            self.results.append(list(S))
            return
        
        S.append(nums[index])
        self.search(nums, S, index + 1)
        S.pop()
        self.search(nums, S, index + 1)
        
    def subsets(self, nums):
        self.results = []
        self.search(sorted(nums), [], 0)
        return self.results
```
Solution 2:
```
class Solution:
    """
    @param nums: A set of numbers
    @return: A list of lists
    """
    def subsets(self, nums):
        nums = sorted(nums)
        combinations = []
        self.dfs(nums, 0, [], combinations)
        return combinations
        
    def dfs(self, nums, index, combination, combinations):
        combinations.append(list(combination))
        
        for i in range(index, len(nums)):
            combination.append(nums[i])
            self.dfs(nums, i + 1, combination, combinations)
            combination.pop()
```
Solution 3:
```
class Solution:
    def subsets(self, nums):
        result = []
        n = len(nums)
        nums.sort()

        # 1 << n is 2^n
        # each subset equals to an binary integer between 0 .. 2^n - 1
        # 0 -> 000 -> []
        # 1 -> 001 -> [1]
        # 2 -> 010 -> [2]
        # ..
        # 7 -> 111 -> [1,2,3]
        for i in range(1 << n):
            subset = []
            for j in range(n):
                if (i & (1 << j)) != 0:
                    subset.append(nums[j])
            result.append(subset)
        return result
```
Solution 4:
```
class Solution:
    def subsets(self, nums):
        results = []

        if not nums:
            return results

        nums.sort()

        # BFS
        queue = deque()
        queue.append([])

        while queue:
            subset = queue.popleft()
            results.append(subset)

            for i in range(len(nums)):
                if not subset or subset[-1] < nums[i]:
                    nextSubset = list(subset)
                    nextSubset.append(nums[i])
                    queue.append(nextSubset)

        return results
```
if that arrray has duplicates, we need to delete duplicates.
```
class Solution:
    """
    @param nums: A set of numbers.
    @return: A list of lists. All valid subsets.
    """
    def subsetsWithDup(self, nums):
        nums = sorted(nums)
        subsets = []
        self.dfs(nums, 0, [], subsets)
        return subsets
        
    def dfs(self, nums, index, subset, subsets):
        subsets.append(list(subset))
        
        for i in range(index, len(nums)):
            if i > index and nums[i] == nums[i - 1]:
                continue
            subset.append(nums[i])
            self.dfs(nums, i + 1, subset, subsets)
            subset.pop()
```
## Example: find all permutations in a set.


### Question: To traverse a graph, should we use BFS or DFS?

when the graph is not directed, we normally use BFS. when the graph is directed, we normally use DFS. 


### Question: what kind of problem in the implicit graph DFS?

For the depth-first search which is not on the binary tree, most of them is about calculation Combination and Permutation. 

