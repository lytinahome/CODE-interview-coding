# Divide Conquer and Traversal

## Template
1, what is the base case
2, what is the relationship between root and left/right 
## Template -- using global variable
```
class solution:
    globalvariable = 0
    def answer(self, root):
        self.helper(root)
        return self.globalvariable
        
    def helper(self, root):
        if root == None:
            return 0 / sys.maxsize / -sys.maxsize
        leftanswer = self.helper(self, root.left)
        rightanswer = self.helper(self, root.right)
        
        self.globalvariable = xx        
```

## Template -- search all paths
method1: append + recursion + pop 
```
class Solution:
    def binaryTreePaths(self, root):
        if root == None:
            return []
        results = []
        self.dfs(root, [], results)    
        return results
        
    def dfs(self, node, path, results):
        path.append(node.val)
        
        if node.left == None and node.right == None: 
            results.append(path.copy())
        if node.left:
            self.dfs(node.left, path, results)
        if node.right:
            self.dfs(node.right, path, results)
   
        path.pop()
        return
```
method2: divide and conquer
```
class solution:
    def binaryTreePath(self, root):
        if root == None:
            return []
        if root.left == None and root.right == None:
            return [[root.value]]
        leftpaths = self.binaryTreePaths(root.left)
        rightpaths = self.binaryTreePaths(root.right)
        
        result = []
        for item in leftpaths+rightpaths:
            result.append([root.val] + item)    
        return result
```
## Template -- Divide and Conquer
```
def dc():
    # the base case
    # recursion
    # update the return value
```
### Questions: three problems related to binary tree:
|  | **find extreme value and path** |
|--|--|
| 1 | 597. subtree with maximum average | 
|  | 596. minimum subtree |
| 1 | 480. binary tree paths|
| 1 | 578. lowest common ancestor III|
| 1 | 474. Lowest Common Ancestor II|
| 1 | 246@. Binary Tree Path Sum II|


|  | **traversal** |
|--|--|
|  | 66. binary tree preorder traversal (non-recursion)|
|  | 66. binary tree preorder traversal|
|  | 68. binary tree preorder traversal (non-recursion)|
|  | 68. binary tree preorder traversal|

|  | **structure change** |
|--|--|
|  | 175. invert binary tree |
|  | 453. flattern binary tree to linked list|


|  | **binary search tree** |
|--|--|
|  | 95. validate binary search tree (non-recursion)|
|  | 95. validate binary search tree|
|  | 67. binary tree inorder traversal (non-recursion)|
|  | 67. binary tree inorder traversal|
|  | 902. kth smallest element in BST|
|  | 86. binary search tree iterator|
|  | 448. inorder successor in BST|
|  | 900. cloest BST value|
|  | 901. cloest BST value II|
|  | 11. search range in BST|
|  | 85. insert node in a BST|
|  | 87. remove node in a BST|
| 1 | 1311. Lowest Common Ancestor of a Binary Search Tree|




### Questions: Binary Tree Traversal
* level order: BFS
* inorder/ preorder/ postorder: DFS

### Questions: relationship between Recursion, Search, Traverse and Divide Conquer
Search: 
- BFS
- DFS (backtracking) 
  - Traversal (recursion // iteration)
  - Divide & Conquer (recursion // iteration)

### Question: Divide Conquer

