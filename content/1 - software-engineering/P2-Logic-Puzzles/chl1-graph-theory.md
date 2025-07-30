

## 802. 寻找最终安全状态


:d Medium
:l https://leetcode.com/problems/find-eventual-safe-states
:t Depth-First Search  深度优先搜索, Breadth-First Search 广度优先搜索
Graph 图形, Topological Sort 拓扑排序

There is a directed graph of `n` nodes with each node labeled from `0` to `n - 1`. The graph is represented by a **0-indexed** 2D integer array `graph` where `graph[i]` is an integer array of nodes adjacent to node `i`, meaning there is an edge from node `i` to each node in `graph[i]`.  
有一个由 `n` 个节点组成的有向图，每个节点的标签从 `0` 到 `n - 1` 。该图用一个**以 0 为索引的**二维整数数组 `graph` 表示，其中 `graph[i]` 是与节点 `i` 相邻的整数数组，这意味着从节点 `i` 到 `graph[i]` 中的每个节点都有一条边。

A node is a **terminal node** if there are no outgoing edges. A node is a **safe node** if every possible path starting from that node leads to a **terminal node** (or another safe node).  
如果一个节点没有出边，则该节点为**终端节点** 。如果从该节点出发的所有可能路径都通向**终端节点** （或另一个安全节点），则该节点为**安全节点** 。

Return _an array containing all the **safe nodes** of the graph_. The answer should be sorted in **ascending** order.  
返回_一个包含图中所有**安全节点**的数组_ 。答案应按**升序**排列。


> ![[Pasted image 20250729220032.png]]
```
Input: graph = [[1,2],[2,3],[5],[0],[5],[],[]]
Output: [2,4,5,6]
Explanation: The given graph is shown above.
Nodes 5 and 6 are terminal nodes as there are no outgoing edges from either of them.
Every path starting at nodes 2, 4, 5, and 6 all lead to either node 5 or 6.
```

Example 2:  示例 2：

```
Input: graph = [[1,2,3,4],[1,2],[3,4],[0,4],[]]
Output: [4]
Explanation:
Only node 4 is a terminal node, and every path starting at node 4 leads to node 4.
```

**Constraints:  限制：**

- `n == graph.length`
- `1 <= n <= 104`
- `0 <= graph[i].length <= n`
- `0 <= graph[i][j] <= n - 1`
- `graph[i]` is sorted in a strictly increasing order.  
    `graph[i]` 按严格递增的顺序排序。
- The graph may contain self-loops.  
    该图可能包含自循环。
- The number of edges in the graph will be in the range `[1, 4 * 104]`. 
    图中的边数在 `[1, 4 * 10 4 ]` 范围内。

### Theory


### Solution



### Pseudocode


> A flowchart of the process





---

Plan

 [图论 - 学习计划 - LeetCode --- Graph Theory - Study Plan - LeetCode](https://leetcode.com/studyplan/graph-theory/)


---

## Problem Name

:d difficulty
:l link
:t tags,tags2

### Theory


### Solution


### Pseudocode


> A flowchart of the process