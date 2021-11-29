# Linked List

## Introduction

Linked list is a simple data structure in programming, which obviously is used to store data and retrieve it accordingly. To make it easier to imagine, it is more like a dynamic array in which data elements are linked via pointers rather than being tightly packed. 

## Creation of List

A linked list is created by using the node class. We create a Node object and create another class to use this ode object. We pass the appropriate values through the node object to point the to the next data elements. The below program creates the linked list with three data elements. In the next section we will see how to traverse the linked list.

### Example

```python
class Node:
   def __init__(self, dataval=None):
      self.dataval = dataval
      self.nextval = None

class SLinkedList:
   def __init__(self):
      self.headval = None

list1 = SLinkedList()
list1.headval = Node("Mon")
e2 = Node("Tue")
e3 = Node("Wed")
# Link first Node to second node
list1.headval.nextval = e2

# Link second Node to third node
e2.nextval = e3

```
## New Nodes

A node is an object which has a data field and a pointer to another node in the linked list. A simple structure of a node can be shown in the following figure.

![Node Explanation](https://www.pythonforbeginners.com/wp-content/uploads/Linked-List-in-Python3.png)

### Example

```python

```
## [Problem to Solve](linkedtree-solution.md)

