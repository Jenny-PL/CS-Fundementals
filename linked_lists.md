# Linked lists

Data structure, similar but different to arrays.

Linked-lists:
- Do not require continous elements
- To get to an element in the middle, must traverse over all others on the way (Thus O(n) time to get to an element)
- Can add/delete at front with O(1) time 
- Can also add/delete from end with 0(1) time if doubly linked list

Benefits:
  - Less size: scalable; only take up precisely as much room as is needed (no extra space at end, etc)
  - When removing from a linked-list, don't have to shift each subsequent item down in position (for an array, when an element is added/removed, all subsequent elements shift up/down so that each takes up consecutive indices.  Not an issue with linked-lists)

How does a linked-list work?
- Each node points to the one(or more) nodes in memory (contains a **reference** to the next (and potentially prior) element)

Singly Linked lists:
  - Each element (node) contains a references to the next node (points to the next node)
  - Each node has two fields: value, next
    - value: value of element
    - next: reference to subsequent node
  - Linked list itself contains reference to ther 1st element (aka head)
    - 0(1) to add element fo front of list(in front of head)
    - however 0(n) to add element to end of list (must iterate through each node to find the next one to get to end.)
  - Last element: value=value, next=null

Doubly linked lists:
- O(1) to add/delete for first or last element of the list, as a doubly linked list has info about head & tail
- Each element (node) contains references to the next node and the previous node:
  - value, next, previous
  - head: value=value, next=next, previous=null
  - tail: value=value, next=null, prev=prev
- Linked list itself maintains reference to 1st and last nodes in the list (head, tail)

## Obj Oriented Design of Linked List

singly linked list
```
# Defines a node in the singly linked list
class Node:
    def __init__(self, value):
        self.val = value
        self.next = None
```
Class for single linked list
```
class LinkedList:
    def __init__(self):
        self.head = None
```
Iterate through singly linked list to check for specific value:
```
 def search(self, value):
    current = self.head

    while current:
        if current.val == value:
            return True
        current = current.next
    
    return False
```
---

Doubly linked list
```
# Defines a node in the doubly linked list
class Node:
    def __init__(self, value):
        self.val = value
        self.next = None
        self.prev = None
```
Class for double linked list
```
class LinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
```

## Abstract Data Types
ABTs are Defined by what they do, not how they're implemented

### Stacks
- linear list of data: LIFO (last in, first out)
- Arrays or linked lists can be used
- Linked lists are popular for implementing stacks, as they can be 0(1) to access front/end of lists.
  - push: puts item at top of the stack (end)
  - pop: removes/returns item at top of the stack (end)
  - peek: shows item at top of stack (end) but doesn't remove it
  - is_empty: returns True is stack is empty
  - size: length

### Queues
- linear list of data: First-In-First-Out (FIFO) order
- doubly linked lists could be a good choice to optimize time complexity
Methods:
    - enqueue(item) - This method puts an item into the back of the queue.
    - dequeue - This method removes and returns the item at the front of the queue.
    - is_empty - returns true if the queue is empty 

