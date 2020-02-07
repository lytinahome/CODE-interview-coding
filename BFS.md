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

|                        | level  | visited  | indegree  |   |
|---|---|---|---|---|
| Level Order Traversal  | [x]  | [x]  | [ ]  |   |
| Connected Component    | [ ]  | [x]  | [ ]  |   |
| Topological Sorting    | [ ]  | [x]  | [x]  |   |
| Traversal in Tree      | [ ]  | [ ]  | [ ]  |   |
| Traversal in Graph     | [ ]  | [x]  | [ ]  |   |
| Shortest dist in Graph | [x]  | [x]  | [ ]  |   |

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

|   |**Traversal in binary tree -- Time complexity $O(nodes)$**|
|---|---|
|   |69. [M] binary Tree Level Order Traversal |
|   |7. [M] serialize and deserialize binary Tree| 
|   |70. [M] Binary Tree Level Order Traversal II|
|   |71. [M] Binary Tree Zigzag Level Order Traversal|
|  1 |242. [E] Convert Binary Tree to Linked Lists by Depth|

|   |**Traversal in graph -- Time complexity $O(nodes+edges)$**|
|---|---|
|   |137. [M] Clone Graph|
|   |120. [M] Word Ladder|
|   |178. [M] Graph Valid Tree|
|   |618. [M] Search Graph Nodes|
|   |431. [M] Connected Component in Undirected Graph|

|   |**Traversal in matrix -- Time complexity $O(rows * columns)$**|
|---|---|
|   |433. [E] Number of Islands|
| 1  |611. [M] Knight Shortest Path|
|   |573. [H] Build Post Office II|
|   |598. [M] Zombie in Matrix|


|   |**Topological Sorting**|
|---|---|
|   |127. [M] Topological Sorting|
|   |615. [M] Course Schedule |
| 1 |616. [M] Course Schedule II|
|  1 |892. [H] Alien Dictionary|
|   |605. [M] Sequence Reconstruction|



### Question, when to use BFS:

**The key is "Search"**, which includes the following applications:
* Traversal in Graph.
  * Level Order Traversal -- Shortest Path in Sinple Undirected Graph.
  * Connected Component
  * Topogical Sorting
* Iteration solution for all possible results.

### Question, about topological sorting:
* find any topological sorting -- BFS
* if there exists topological sorting -- BFS
* find all topological sorting -- DFS
* if there is only one topological sorting -- BFS check if ```len(Q)``` always equals to 1.

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

### Follow up, Bidirectional BFS



