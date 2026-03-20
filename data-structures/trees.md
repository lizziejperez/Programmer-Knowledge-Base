# Trees

A **tree** is a hierarchical data structure consisting of nodes connected by edges.

## Table of Contents

* [Key Characteristics](#1-key-characteristics)
* [Time Complexity](#2-time-complexity-binary-tree)
* [Structure](#3-structure)
* [Common Operations](#4-common-operations)
* [Variants](#5-variants)
* [Use Cases](#6-use-cases)
* [Advantages & Disadvantages](#7-advantages--disadvantages)
* [Interview Patterns](#8-interview-patterns)

## 1. Key Characteristics

* Hierarchical structure
* Root node
* Parent-child relationships
* No cycles

## 2. Time Complexity (Binary Tree)

| Operation | Time |
| --------- | ---- |
| Search    | O(n) |
| Insert    | O(n) |
| Delete    | O(n) |

Balanced trees: O(log n)

## 3. Structure

```
  10
 /  \
5    15
```

## 4. Common Operations

### Traversal

Traversal is the process of visiting all nodes in a tree.

Types of Traversal:

* Inorder
* Preorder
* Postorder

#### Inorder Traversal (Left → Root → Right)

Used in binary search trees to retrieve values in sorted order.

Example:

```
def inorder(node):
    if node:
        inorder(node.left)
        print(node.value)
        inorder(node.right)
```

#### Preorder Traversal (Root → Left → Right)

Useful for copying or serializing a tree.

```
def preorder(node):
    if node:
        print(node.value)
        preorder(node.left)
        preorder(node.right)
```

#### Postorder Traversal (Left → Right → Root)

Useful for deleting or freeing a tree.

```
def postorder(node):
    if node:
        postorder(node.left)
        postorder(node.right)
        print(node.value)
```

### Insertion (Binary Search Tree)

Insert a value while maintaining ordering:

```
def insert(root, value):
    if root is None:
        return Node(value)
    if value < root.value:
        root.left = insert(root.left, value)
    else:
        root.right = insert(root.right, value)
    return root
```

### Search (Binary Search Tree)

```
def search(root, value):
    if root is None or root.value == value:
        return root
    if value < root.value:
        return search(root.left, value)
    return search(root.right, value)
```

## 5. Variants

### Binary Tree

Each node has at most two children.

Used as a general-purpose hierarchical structure.

### Binary Search Tree (BST)

Left subtree values < root < right subtree values.

Properties:

* Enables efficient search
* Inorder traversal returns sorted data

### AVL Tree

A self-balancing binary search tree.

* Maintains height balance
* Ensures O(log n) operations

### Red-Black Tree

A balanced tree with color-based rules.

* Used in many standard libraries
* Guarantees near O(log n) performance

### Heap (Specialized Tree)

A complete binary tree used for priority access.

* Min heap: smallest element at root
* Max heap: largest element at root

(Heaps are covered separately in heap data structures)

## 6. Use Cases

* Hierarchical data
* File systems
* Databases
* Expression trees

## 7. Advantages & Disadvantages

**Advantages**

* Efficient hierarchical representation

**Disadvantages**

* Can become unbalanced

## 8. Interview Patterns

Common problem-solving patterns involving trees:

* **Depth-first search (DFS)**: Traverse nodes recursively or using a stack

  * Example: https://leetcode.com/problems/binary-tree-inorder-traversal/

* **Breadth-first search (BFS)**: Traverse level-by-level using a queue

  * Example: https://leetcode.com/problems/binary-tree-level-order-traversal/

* **Recursive divide and conquer**: Solve subtrees and combine results

  * Example: https://leetcode.com/problems/maximum-depth-of-binary-tree/

* **Tree traversal patterns**: Inorder, preorder, postorder

  * Example: https://leetcode.com/problems/binary-tree-preorder-traversal/

* **Lowest common ancestor (LCA)**: Find shared ancestor of two nodes

  * Example: https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/