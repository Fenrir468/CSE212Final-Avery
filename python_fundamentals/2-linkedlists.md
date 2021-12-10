# Doubly Linked List

## Introduction

Linked list is a simple data structure in programming, which obviously is used to store data and retrieve it accordingly. To make it easier to imagine, it is more like a dynamic array in which data elements are linked via pointers rather than being tightly packed. 

![Linked List](https://byui-cse.github.io/cse212-course/lesson07/linked_list.jpeg)

Common Linked List Operation | Description
---------------------- | -----------
insert_head(value) | Adds "value" before the head
insert_tail(value) | Adds "value" after the tail
insert(i, value) | Adds "value" after node "i".
remove_head() | Removes the first item (the head)
remove_tail(index) | Removes the last item (the tail)
remove(i) | 	Removes node "i".
size() | Return the size of the linked list
empty() | Returns true if the length of the linked list is zero.

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
## Implementation of Doubly Linked List
We will implement doubly linked list using some concepts of object oriented programming in python. We will first create a class for creating a node in a basic linked list, with three attributes: the data, previous pointer and next pointer. The code looks like this:
```python
class Node:
    def __init__(self, data):
        self.item = data
        self.next = None
        self.prev = None
``` 

The item variable will store the actual element of the node. The next stores the address to the next node, while prev stores the address to the previous node in the doubly linked list.

In the next step, we will create a doublyLinkedList class, that contains different functions to insert, delete and display elements of doubly linked list.
```python
class doublyLinkedList:
    def __init__(self):
        self.start_node = None
 ``` 
The most permissive way to insert an element in a doubly linked list is to insert the element in the empty list. The following piece of code enters an element at the origin of the doubly linked list:
```python
    def InsertToEmptyList(self, data):
        if self.start_node is None:
            new_node = Node(data)
            self.start_node = new_node
        else:
            print("The list is empty")
 ```
## Inserting Items at the End
Inserting an element at the end of the doubly linked list is slightly alike to inserting an element at the start of the list. Before entering the elements, we need to verify and check if the doubly linked list is empty. If the list is empty then we can easily use the function InsertToEmptyList() method to insert the element to the list. If the list already has added element, we iterate through the list till the address to the next node reaches NULL. When the next node address becomes NULL, it denotes that the current node is the last node.

The previous reference for the new node is set to the last node, and the next address for the last node is assigned to the newly inserted node. The function for inserting an item at the last node is as follows:

```python
    # Insert element at the end
    def InsertToEnd(self, data):
        # Check if the list is empty
        if self.start_node is None:
            new_node = Node(data)
            self.start_node = new_node
            return
        n = self.start_node
        # Iterate till the next reaches NULL
        while n.next is not None:
            n = n.next
        new_node = Node(data)
        n.next = new_node
        new_node.prev = n
 ```
 
## Deleting Elements from the Start
The most natural way to delete an element from a doubly linked list is deleting from the start of the list. In order to achieve this, we will assign the value of the start node to the next node and then assign the previous address of the start node to NULL. But before doing this, we need to check two things. First, we need to check if the list is empty. And then we have to verify if the list has only one node or not. If the list has only one element then we can easily assign the start node to NULL. The following code can be utilised to delete node from the start of the doubly linked list.

 
```python
    # Delete the elements from the start
    def DeleteAtStart(self):
        if self.start_node is None:
            print("The Linked list is empty, no element to delete")
            return 
        if self.start_node.next is None:
            self.start_node = None
            return
        self.start_node = self.start_node.next
        self.start_prev = None;
 ```
 
## Deleting Elements from the End
To remove the element from the end, we have to again verify if the list is empty or if the list has a single element. If the list has a single element, we will assign the start node to NULL. If the doubly linked list has more than one element, we traverse through the list until the last node reaches NULL. Once we reach the last node, we assign the next address of the node previous to the last node, to NULL which actually deletes the last node. The following function can be used to delete the element from the end of the list.

 
```python
    # Delete the elements from the end
    def delete_at_end(self):
        # Check if the List is empty
        if self.start_node is None:
            print("The Linked list is empty, no element to delete")
            return 
        if self.start_node.next is None:
            self.start_node = None
            return
        n = self.start_node
        while n.next is not None:
            n = n.next
        n.prev.next = None
 ```
## Traversing the Linked List
Display the elements in the doubly linked list, while iterating through each element.

```python
    # Traversing and Displaying each element of the list
    def Display(self):
        if self.start_node is None:
            print("The list is empty")
            return
        else:
            n = self.start_node
            while n is not None:
                print("Element is: ", n.item)
                n = n.next
        print("\n")
```

## Importance of a Linked List
A linked list saves memory. It only allocates the memory required for values to be stored. In arrays, you have to set an array size before filling it with values, which can potentially waste memory. Linked list nodes can live anywhere in the memory.

## Problem to Solve
Write a Python program to access a specific item in a singly linked list using index value.
```python
class Node:
    # Singly linked node
    def __init__(self, data=None):
        self.data = data
        self.next = None
class singly_linked_list:
    def __init__(self):
        # Createe an empty list
        self.tail = None
        self.head = None
        self.count = 0
	
    def append_item(self, data):
        #Append items on the list
        # Insert personal code
    
    def __getitem__(self, index):
        # Insert personal code

#Test
items = singly_linked_list()
items.append_item('PHP')
items.append_item('Python')
items.append_item('C#')
items.append_item('C++')
items.append_item('Java')

print("Search using index:")
print(items[0])
print(items[1])
print(items[4])
print(items[5])
print(items[10])
```
## [Example Solution](linkedtree-solution.md)
