# BFS summary

## BFS template -- classic:
```diff
 from collections import deque 
 Q = deque()
-visited = set()

-visited.add(start)
 Q.append(start)
+level = 0

 while Q:
+    for _ in range(len(Q)):
         current = Q.popleft()
         # add the operation to current
         for neighbor in current.neighbors:
             if neighbor not in visited:
-                visited.add(neighbor)
                 Q.append(neighbor)
+    level += 1    
```

Note1: always check whether the new item is in visited set in order to elimate duplicates and unnecessary calculation.
Note2: first add item to the visited set, then put it to the Q in order to avoid duplicate.
## BFS template -- use Dummy Node to count level:
```
from collections import deque
Q = deque()
visited = set()

visited.add(start)
Q.append(start)
Q.append(None)
level = 0

while len(Q)>1:
    current = Q.popleft()
    if current == None:
        level += 1
        Q.append(None)
    else:
        for neighbor in current.neighbors:
            if neighbor not in visited:
                visted.add(neighbor)
                Q.append(neighbor)

```

## BFS template -- use two queue to count level:
```
from collections import deque
Q1, Q2 = deque(), deque()
visited = set()

visited.add(start)
Q1.append(start)
level = 0

while Q1:
    while Q1:
        current = Q1.popleft()
        for neighbor in Q1.neighbors:
            if neighbor not in visited:
                visited.add(neighbor)
                Q2.append(neighbor)
    level += 1
    Q1, Q2 = Q2, Q1
    
```

## the summary of lintcode

* Traversal in binary tree
69. binary Tree Level Order Traversal 

### Question, when to use BFS:

**The key is "Search"**, which includes the following applications:
* Traversal in Graph.
  * Level Order Traversal -- Shortest Path in Sinple Undirected Graph.
  * Connected Component
  * Topogical Sorting
* Iteration solution for all possible results.

### Question, which objects can be applied to BFS:

* Binary Tree

Note: Binary Tree is a special case of directed graph. As there is no circle in a tree, there is no need to use a Hashset to record the visited point.
* Graph
* Matrix
* Topological

### Question, how to represent a graph:
* Adjacency Matrix (not used in practice since it is space consuming)
* Adjacency List
To realize a adjacency list in python, one can use set + map
``` 
adjacency_list = {x: set() for x in nodes}
```
or define a class such like
```
class GraphNode:
  def __init__(self, label):
    self.label = label
    self.neighbors = [] # a list of GraphNodes
```
the space complexity is $O(m)$, where $m$ is the number of edges (the worst case is $O(n^2)$).
Note that the indegree table is necessary for finding the topological order.


