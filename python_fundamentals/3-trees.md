#### [Welcome](0-welcome.md)
# Tree

## Introduction

Common Binary Search Tree Operation | Description 
A binary tree is a data structure in which every node or vertex has atmost two children. In Python, a binary tree can be represented in different ways with different data structures(dictionary, list) and class representation for a node.

Common Binary Search Tree Operation | Description
---------------------- | -----------  
insert(value) | Insert a value into the tree.
remove(value) | Remove a value from the tree.
contains(value) | Determine if a value is in the tree.
traverse_forward | Visit all objects from smallest to largest. 
traverse_reverse | Visit all objects from largest to smallest.
height(node) | Determine the height of a node. If the height of the tree is needed, the root node is provided.
size() | Return the size of the Binary Search Tree.
empty() | 	Returns true if the root node is empty. This can also be done by checking the size for 0.

## Binary Tree
![Binary Tree](https://byui-cse.github.io/cse212-course/lesson09/binary_tree.jpeg)

### Example

```python

```

## Binary Search Tree
A binary search tree is a binary tree that follows rules for data that is put into the tree. Data is placed into the BST by comparing the data with the value in the parent node. If the data being added is less than the parent node, then it is put in the left subtree. If the data being added is greater than the parent node, then it is put in the right subtree. If duplicates are allowed than the duplicate can be put either to the left or to the right of the root. By using this process, the data is stored in the tree sorted.

### Example

```python

```

## Ballanced Binary Search Tree
A balanced binary search tree is a BST such that the difference of height between any two subtrees is not dramatically different. The height of a tree can be found by counting the maximum number of nodes between root and the leaves. Since it is not reasonable to expect that the order of data will result in a balanced BST, numerous algorithms have been written to detect if a tree is unbalanced and to correct the unbalance. 

### Example

```python

```

## Inserting into a Binary Search Tree


### Example

```python

```
## Travsering a Binary Search Tree

The tree can be traversed by deciding on a sequence to visit each node. As we can clearly see we can start at a node then visit the left sub-tree first and right sub-tree next. Or we can also visit the right sub-tree first and left sub-tree next. Accordingly there are different names for these tree traversal methods.

### Example

```python

```

## Problem to Solve
```python
class TreeNode(object):
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

def array_to_bst(array_nums):
        # Insert own code 

def preOrder(node): 
        # Insert own code    

array_nums = [1,2,3,4,5,6,7]

print("Original array:")
print(array_nums)
result = array_to_bst(array_nums)
print("\nArray to a height balanced BST:")
print(preOrder(result))
```
## [Example Solution](tree_solution.md)
