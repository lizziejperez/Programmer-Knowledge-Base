# Graph Algorithms

Graph algorithms operate on graphs, which are collections of vertices connected by edges.

## Table of Contents

* [Overview](#1-overview)
* [Common Graph Problems](#2-common-graph-problems)
* [Breadth-First Search (BFS)](#3-breadth-first-search-bfs)
* [Depth-First Search (DFS)](#4-depth-first-search-dfs)
* [Shortest Path](#5-shortest-path)
* [Minimum Spanning Tree](#6-minimum-spanning-tree)
* [Use Cases](#7-use-cases)
* [Interview Patterns](#8-interview-patterns)

## 1. Overview

Graph algorithms are used to solve problems involving:

* **Connectivity**: Determine whether vertices are connected and identify connected components.
* **Traversal**: Visit nodes in a graph systematically, often using BFS or DFS.
* **Shortest paths**: Find the minimum-distance path between vertices.
* **Dependencies**: Model tasks or relationships where one item depends on another.
* **Spanning structures**: Connect all vertices using a subset of edges, often with minimum total cost.

In graph complexity:

* **V** = number of vertices
* **E** = number of edges

## 2. Common Graph Problems

Common categories include:

* visiting all nodes
* finding connected components
* finding shortest paths
* detecting cycles
* building minimum spanning trees

## 3. Breadth-First Search (BFS)

BFS explores level by level and is useful for shortest paths in unweighted graphs.

### Idea

* Start from a source node
* Visit all neighbors
* Then visit neighbors of neighbors

### Running Time

* O(V + E)

## 4. Depth-First Search (DFS)

DFS explores as far as possible before backtracking.

### Idea

* Start from a source node
* Follow one path deeply
* Backtrack when needed

### Running Time

* O(V + E)

## 5. Shortest Path

### Unweighted Graphs

Use BFS.

### Weighted Graphs

Common algorithm: Dijkstra’s algorithm

### Dijkstra’s Idea

* Maintain best known distance to each node
* Repeatedly choose the node with smallest tentative distance
* Relax outgoing edges

## 6. Minimum Spanning Tree

A **spanning tree** connects all vertices without cycles.

A **minimum spanning tree (MST)** is a spanning tree with the smallest possible total edge weight.

Common algorithms:

### I. Prim’s Algorithm

Prim’s algorithm builds the MST by **growing a single tree**.

#### Idea

* Start from any vertex
* Repeatedly add the smallest edge that connects a new vertex to the tree
* Continue until all vertices are included

#### Steps

1. Start with one vertex
2. Add all its edges to a priority queue
3. Select the smallest edge that connects to a new vertex
4. Add that vertex to the tree
5. Repeat until all vertices are included

#### Pseudocode

```text
start with any vertex
mark it as visited
add its edges to a min heap

while heap is not empty:
    edge = smallest edge from heap
    if edge leads to unvisited vertex:
        add edge to MST
        mark vertex as visited
        add its edges to heap
```

#### Time Complexity

* Using min heap: O(E log V)

### II. Kruskal’s Algorithm

Kruskal’s algorithm builds the MST by **selecting edges globally**.

#### Idea

* Sort all edges by weight
* Add edges one by one
* Only add an edge if it does not form a cycle

#### Steps

1. Sort all edges in increasing order
2. Initialize each vertex as its own set
3. Iterate through edges:

   * If adding the edge does not create a cycle, include it
4. Stop when MST has V - 1 edges

#### Pseudocode

```text
sort all edges by weight

for each edge (u, v):
    if u and v are in different sets:
        add edge to MST
        union(u, v)
```

#### Time Complexity

* Sorting edges: O(E log E)
* Union-Find operations: near O(1)
* Overall: O(E log E)

### Key Difference

* **Prim’s**: grows one connected tree (node-focused)
* **Kruskal’s**: builds from edges (edge-focused)

### When to Use

* Use **Prim’s** when the graph is dense
* Use **Kruskal’s** when the graph is sparse

## 7. Use Cases

* GPS and route planning
* Dependency resolution
* Social networks
* Network routing

## 8. Interview Patterns

Common problem-solving patterns involving graph algorithms:

* **BFS on grids and graphs**: Level-order traversal and shortest path in unweighted graphs
  * Example: https://leetcode.com/problems/shortest-path-in-binary-matrix/

* **DFS for components and traversal**: Explore regions or connected components
  * Example: https://leetcode.com/problems/number-of-islands/

* **Cycle detection / topological ordering**: Directed dependency problems
  * Example: https://leetcode.com/problems/course-schedule/

* **Union-Find / connectivity**: Grouping and component tracking
  * Example: https://leetcode.com/problems/number-of-provinces/