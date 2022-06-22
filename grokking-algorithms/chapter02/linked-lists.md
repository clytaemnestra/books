## Creation
### Principle:
* in C it's represented by using structures, in Python or C++ by class
* classes
    * three important things:
        * node -> node object
        * data -> data assigned to the given node 
        * head -> first node
    * first class is a node, which consists of data and pointer to the next one (pointer is intialized as null)
    * second class is Linked List, which consist of head, which is also initiaulized as None 

### Code
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None
```

## Creation of a linked list
### Principle
* create an empty linked list 
* add head and assign to it data (data is in class Node)
* add second node and assign to it data
* add third node and assign to it data
* link head with second node 
* link second with the third node
* third node has default `None`, so no need to do anything with it

### Code
```python
llist = LinkedList()
llist.head = Node(1)
second = Node(2)
third = Node(3)

llist.head.next = second
second.next = third
```
## Insertion 
### Beginning
### Principle
* create a new node and add data to it
* switch head & new node:  
    * as next add there current head
    * move head to the new node

### Code
```python
def insert(self, data):
    new_node = Node(data)
    new_node.next = self.head
    self.head = new_node
```
### After a given node 
### Principle
* create a new node and add data do it 
* change next of the previous node
* set up next to point to the next node

### Code
```python
def insert_after(self, previous, data):
    new_node = Node(data)
    new_node.next = previous.next
    previous.next = new_node
```

### End
### Principle
* create a new node and add data to it (next is by default `None`)
* set up previous next from `NULL` to new node

### Code
```python
def append(self, data):
    new_node = Node(data)
    # if the list is empty, make the new node as head
    if self.head is None:
        self.head = new_node
        return
    # else traverse till the last node
    # set up first one as 'last'
    # while there is node that has 'next' 
    # set up last as the current node
    last = self.head 
    while last.next:
        last = last.next
    
    # change the next of last node
    last.next = new_node 
    
```

## Deletion
### Principle 
* store the head node 
* if head node stores the key to be deleted, then set up the next node as head
* if not, search for the key to be deleted -> until it's not `None`
* when it finds the key:
    * save the current node as previous
    * save the next as current
* unlink the node from the list     

### Code
```python
def delete(self, key):
    to_delete = self.head 
    # if head node is to be deleted
    if to_delete is not None:
        if to_delete.data == key:
            self.head = to_delete.next
            to_delete = None
            return 

    while to_delete is not None:
        if to_delete.data == key:
            break
        previous = to_delete
        to_delete = to_delete.next

    previous.next = to_delete.next
    to_delete = None
```

## Reverse
### Principle 
* initialize 2 pointers: previous, current 
* loop over linked list  
* store next node (next as next of current)
* reverse - change next of current to previous
* move previous to current and then move current to next 
* set head as previous 

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/RGIF2.gif)

### Code
```python
def reverse(self):
    previous = None
    current = self.head 
    
    while current is not None:
        next = current.next 
        current.next = previous 
        previous = current
        current = next 
    self.head = previous
        
```
