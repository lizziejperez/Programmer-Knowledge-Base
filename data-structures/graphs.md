# Graphs

A **graph** is a collection of nodes (vertices) connected by edges.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Types](#2-types)
* [Time Complexity](#3-time-complexity)
* [Representation](#4-representation)
* [Traversal](#5-traversal)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)

## 1. Key Characteristics

* Nodes (vertices) and edges
* Can be directed or undirected
* May contain cycles

## 2. Types

* Directed vs Undirected
* Weighted vs Unweighted
* Cyclic vs Acyclic

## 3. Time Complexity

Depends on representation:

| Operation | Time     |
| --------- | -------- |
| Add edge  | O(1)     |
| Search    | O(V + E) |

Where:

* V = vertices
* E = edges

## 4. Representation

Graphs are commonly represented in two ways:

### Adjacency List

Each node stores a list of its neighbors.

Example:

```id="adj-list"
graph = {
    1: [2, 3],
    2: [1, 4],
    3: [1],
    4: [2]
}
```

Advantages:

* Space efficient
* Good for sparse graphs

### Adjacency Matrix

A 2D matrix where each cell represents an edge.

Example:

```id="adj-matrix"
    1  2  3  4
1 [ 0, 1, 1, 0 ]
2 [ 1, 0, 0, 1 ]
3 [ 1, 0, 0, 0 ]
4 [ 0, 1, 0, 0 ]
```

Advantages:

* Fast edge lookup (O(1))
* Simpler structure

Disadvantages:

* Uses more memory (O(V^2))

## 5. Traversal

### Depth-First Search (DFS)

* Explores as far as possible before backtracking.
* Uses recursion or a stack.

Example:

```id="dfs"
def dfs(graph, node, visited):
    if node not in visited:
        print(node)
        visited.add(node)
        for neighbor in graph[node]:
            dfs(graph, neighbor, visited)
```

Step-by-step:

```
Start at 1 → go to 2 → go to 4 → backtrack → visit 3
```

### Breadth-First Search (BFS)

* Explores neighbors level by level.
* Uses a queue.

Example:

```id="bfs"
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])

    while queue:
        node = queue.popleft()
        if node not in visited:
            print(node)
            visited.add(node)
            queue.extend(graph[node])
```

Step-by-step:

```
Start at 1 → visit 2, 3 → then visit 4
```

## 6. Use Cases

* Social networks
* Navigation systems (GPS)
* Dependency graphs
* Network routing

## 7. Advantages & Disadvantages

**Advantages**

* Models complex relationships
* Highly flexible

**Disadvantages**

* More complex than linear structures
* Can be memory intensive

## 8. Interview Patterns

Common problem-solving patterns involving graphs:

* **Depth-first search (DFS)**: Explore as far as possible before backtracking

  * Example: https://leetcode.com/problems/number-of-islands/

* **Breadth-first search (BFS)**: Find shortest path in unweighted graphs

  * Example: https://leetcode.com/problems/shortest-path-in-binary-matrix/

* **Cycle detection**: Detect loops in directed or undirected graphs

  * Example: https://leetcode.com/problems/course-schedule/

* **Topological sorting**: Order nodes in a directed acyclic graph

  * Example: https://leetcode.com/problems/course-schedule-ii/

* **Union-Find (Disjoint Set)**: Track connected components

  * Example: https://leetcode.com/problems/number-of-provinces/