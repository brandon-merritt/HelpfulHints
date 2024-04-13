Python Data Structures

1. **Lists**:
   - A list is a collection of items that are ordered and mutable (changeable). Lists are defined by square brackets `[]`.
   ```python
   my_list = [1, 2, 3, 4, 5]
   print(my_list)
   ```

2. **Tuples**:
   - A tuple is a collection of items that are ordered and immutable (unchangeable). Tuples are defined by parentheses `()`.
   ```python
   my_tuple = (1, 2, 3, 4, 5)
   print(my_tuple)
   ```

3. **Sets**:
   - A set is a collection of unique items that are unordered and mutable. Sets are defined by curly braces `{}`.
   ```python
   my_set = {1, 2, 3, 4, 5}
   print(my_set)
   ```

4. **Dictionaries**:
   - A dictionary is a collection of key-value pairs that are unordered and mutable. Dictionaries are defined by curly braces `{}` and consist of key-value pairs separated by colons `:`.
   ```python
   my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}
   print(my_dict)
   ```

5. **Stacks**:
   - A stack is a collection of items that follow the Last In, First Out (LIFO) principle. It supports two main operations: push (adds an item to the top of the stack) and pop (removes the top item from the stack).
   ```python
   class Stack:
       def __init__(self):
           self.items = []

       def push(self, item):
           self.items.append(item)

       def pop(self):
           return self.items.pop()

   stack = Stack()
   stack.push(1)
   stack.push(2)
   stack.push(3)
   print(stack.pop())  # Output: 3
   ```

6. **Queues**:
   - A queue is a collection of items that follow the First In, First Out (FIFO) principle. It supports two main operations: enqueue (adds an item to the rear of the queue) and dequeue (removes the front item from the queue).
   ```python
   from collections import deque

   class Queue:
       def __init__(self):
           self.items = deque()

       def enqueue(self, item):
           self.items.append(item)

       def dequeue(self):
           return self.items.popleft()

   queue = Queue()
   queue.enqueue(1)
   queue.enqueue(2)
   queue.enqueue(3)
   print(queue.dequeue())  # Output: 1
   ```

7. **Linked Lists**:
   - A linked list is a collection of nodes where each node contains a data value and a reference (pointer) to the next node in the sequence. Linked lists can be singly linked (each node has a reference to the next node) or doubly linked (each node has references to both the next and previous nodes).
   ```python
   class Node:
       def __init__(self, data):
           self.data = data
           self.next = None

   class LinkedList:
       def __init__(self):
           self.head = None

       def append(self, data):
           new_node = Node(data)
           if not self.head:
               self.head = new_node
               return
           current = self.head
           while current.next:
               current = current.next
           current.next = new_node

   linked_list = LinkedList()
   linked_list.append(1)
   linked_list.append(2)
   linked_list.append(3)
   ```

8. **Trees**:
   - A tree is a hierarchical data structure that consists of nodes connected by edges. It starts with a root node and each node can have zero or more child nodes. Trees can be binary trees (each node has at most two children) or n-ary trees (each node has up to n children).
   ```python
   class TreeNode:
       def __init__(self, data):
           self.data = data
           self.children = []

       def add_child(self, child):
           self.children.append(child)

   root = TreeNode('A')
   child1 = TreeNode('B')
   child2 = TreeNode('C')
   root.add_child(child1)
   root.add_child(child2)
   ```

These examples cover a range of common data structures implemented in Python. Each data structure comes with its own set of operations and methods for manipulation and retrieval of data. Let me know if you need more details or examples on any specific data structure!