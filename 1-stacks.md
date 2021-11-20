# Stacks

## Introduction

A stack is a linear data structure that stores items in a Last-In/First-Out (LIFO) or First-In/Last-Out (FILO) manner. In stack, a new element is added at one end and an element is removed from that end only. The insert and delete operations are often called push and pop.

## Push

The operation to insert elements in a stack is called push. When we push the book on a stack, we put the book on the previous top element which means that the new book becomes the top element. This is what we mean when we use the push operation, we push elements onto a stack. We insert elements onto a stack and the last element to be pushed is the new top of the stack.

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
## Pop

There is another operation that we can perform on the stack, popping. Popping is when we take the top book of the stack and put it down. This implies that when we remove an element from the stack, the stack follows the First-In, Last Out property. This means that the top element, the last to be inserted, is removed when we perform the pop operation.

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
## Problem to Solve