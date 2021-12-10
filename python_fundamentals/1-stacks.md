#### [Welcom](0-welcome.md)
# Stacks

![Stack Diagram](https://www.onlinetutorialspoint.com/wp-content/uploads/2020/12/Python-Stack-Datastruture-Implementation-1200x496.png)

## Introduction

A stack is a linear data structure that stores items in a Last-In/First-Out (LIFO) or First-In/Last-Out (FILO) manner. In stack, a new element is added at one end and an element is removed from that end only. The insert and delete operations are often called push and pop.

In Python, a stack can be represented using a list. To push an item to the back of the stack, the append function can be used on the list. To pop items from the back of the stack, the pop function can be used. The pop function will also delete it from the list. The size can be determined by using the len function on the list. The performance of the stack using a Python list is based on the performance of the dynamic array.


Common Stack Operation | Description | Performance 
---------------------- | ----------- | ----------- 
push(value) | Adds "value" to the back of the stack. | Performance of adding to the end of a dynamic array
pop() | Removes and returns the item from the back of the stack. | Performance of removing from the end of a dynamic array
size() | Return the size of the stack. | Performance of returning the size of the dynamic array
empty() | Returns true if the length of the stack is zero. | Performance of checking the size of the dynamic array

## Push

The operation to insert elements in a stack is called push. When we push on a stack, we put the element on the previous top element which means that the new element becomes the top element. This is what we mean when we use the push operation, we push elements onto a stack. We insert elements onto a stack and the last element to be pushed is the new top of the stack.

### Example

```python
def push(self,data):
        temp=Node(data)
        if self.top is None:
            self.top=temp
            self.stackSize= self.stackSize+1
        else:
            temp.next=self.top
            self.top=temp
            self.stackSize=self.stackSize+1
```
### Example 2
```python
class Stack:
   def __init__(self):
      self.stack = []

   def add(self, dataval):
# Use list append method to add element
      if dataval not in self.stack:
         self.stack.append(dataval)
         return True
      else:
         return False
# Use peek to look at the top of the stack
   def peek(self):     
	   return self.stack[-1]

AStack = Stack()
AStack.add("Mon")
AStack.add("Tue")
AStack.peek()
print(AStack.peek())
AStack.add("Wed")
AStack.add("Thu")
print(AStack.peek())
```
## Pop

There is another operation that we can perform on the stack, popping. Popping is when we take the top of the stack and put it down. This implies that when we remove an element from the stack, the stack follows the First-In, Last Out property. This means that the top element, the last to be inserted, is removed when we perform the pop operation.

### Example

```python
def pop(self):
        try:
            if self.top == None:
                raise Exception("Stack is Empty")
            else:
                temp=self.top
                self.top=self.top.next
                tempdata=temp.data
                self.stackSize= self.stackSize-1
                del temp
                return tempdata
        except Exception as e:
            print(str(e))
```

### Example 2

```python
class Stack:
   def __init__(self):
      self.stack = []

   def add(self, dataval):
# Use list append method to add element
      if dataval not in self.stack:
         self.stack.append(dataval)
         return True
      else:
         return False
        
# Use list pop method to remove element
   def remove(self):
      if len(self.stack) <= 0:
         return ("No element in the Stack")
      else:
         return self.stack.pop()

AStack = Stack()
AStack.add("Mon")
AStack.add("Tue")
AStack.add("Wed")
AStack.add("Thu")
print(AStack.remove())
print(AStack.remove())
```

## Problem to Solve

- Given a string(S) of lowercase letters remove all duplicate letters.
- Make duplicate removals on string until we no longer can.
- Return the final string after all such duplicate removals have been made. 

```python
def removeDuplicates(S):
        # Insert own code 
# test
S = "thisisatest"
```
### [Example Solution](stack_solution.md)

