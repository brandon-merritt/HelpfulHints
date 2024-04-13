1. **Sorting Algorithms**:

   a. Bubble Sort:
   ```python
   def bubble_sort(arr):
       n = len(arr)
       for i in range(n):
           for j in range(0, n-i-1):
               if arr[j] > arr[j+1]:
                   arr[j], arr[j+1] = arr[j+1], arr[j]
   
   arr = [64, 34, 25, 12, 22, 11, 90]
   bubble_sort(arr)
   print("Sorted array:", arr)
   ```

   b. Merge Sort:
   ```python
   def merge_sort(arr):
       if len(arr) > 1:
           mid = len(arr) // 2
           L = arr[:mid]
           R = arr[mid:]
   
           merge_sort(L)
           merge_sort(R)
   
           i = j = k = 0
           while i < len(L) and j < len(R):
               if L[i] < R[j]:
                   arr[k] = L[i]
                   i += 1
               else:
                   arr[k] = R[j]
                   j += 1
               k += 1
   
           while i < len(L):
               arr[k] = L[i]
               i += 1
               k += 1
   
           while j < len(R):
               arr[k] = R[j]
               j += 1
               k += 1
   
   arr = [64, 34, 25, 12, 22, 11, 90]
   merge_sort(arr)
   print("Sorted array:", arr)
   ```

2. **Searching Algorithms**:

   a. Binary Search:
   ```python
   def binary_search(arr, target):
       low, high = 0, len(arr) - 1
       while low <= high:
           mid = (low + high) // 2
           if arr[mid] == target:
               return mid
           elif arr[mid] < target:
               low = mid + 1
           else:
               high = mid - 1
       return -1

   arr = [2, 3, 4, 10, 40]
   target = 10
   result = binary_search(arr, target)
   if result != -1:
       print("Element is present at index", result)
   else:
       print("Element is not present in the array")
   ```

   b. Linear Search:
   ```python
   def linear_search(arr, target):
       for i in range(len(arr)):
           if arr[i] == target:
               return i
       return -1

   arr = [10, 20, 30, 40, 50]
   target = 30
   result = linear_search(arr, target)
   if result != -1:
       print("Element is present at index", result)
   else:
       print("Element is not present in the array")
   ```

3. **Graph Algorithms**:

   a. Depth-First Search (DFS):
   ```python
   def dfs(graph, start):
       visited = set()
       stack = [start]
       while stack:
           vertex = stack.pop()
           if vertex not in visited:
               print(vertex, end=" ")
               visited.add(vertex)
               stack.extend(reversed(graph[vertex]))  # Reversed to maintain order

   graph = {'A': ['B', 'C'],
            'B': ['D', 'E'],
            'C': ['F'],
            'D': [],
            'E': ['F'],
            'F': []}

   dfs(graph, 'A')
   ```

   b. Breadth-First Search (BFS):
   ```python
   from collections import deque

   def bfs(graph, start):
       visited = set()
       queue = deque([start])
       while queue:
           vertex = queue.popleft()
           if vertex not in visited:
               print(vertex, end=" ")
               visited.add(vertex)
               queue.extend(graph[vertex])

   graph = {'A': ['B', 'C'],
            'B': ['D', 'E'],
            'C': ['F'],
            'D': [],
            'E': ['F'],
            'F': []}

   bfs(graph, 'A')
   ```

4. **Tree Algorithms**:

   a. Tree Traversal (Inorder, Preorder, Postorder):
   ```python
   class TreeNode:
       def __init__(self, value):
           self.value = value
           self.left = None
           self.right = None

   def inorder_traversal(node):
       if node:
           inorder_traversal(node.left)
           print(node.value, end=" ")
           inorder_traversal(node.right)

   root = TreeNode(1)
   root.left = TreeNode(2)
   root.right = TreeNode(3)
   root.left.left = TreeNode(4)
   root.left.right = TreeNode(5)

   print("Inorder Traversal:", end=" ")
   inorder_traversal(root)
   ```

5. **Dynamic Programming**:

   a. Fibonacci Sequence:
   ```python
   def fibonacci(n):
       if n <= 1:
           return n
       else:
           return fibonacci(n-1) + fibonacci(n-2)

   n = 10
   print("Fibonacci Sequence:")
   for i in range(n):
       print(fibonacci(i), end=" ")
   ```

6. **String Algorithms**:

   a. String Matching (Naive):
   ```python
   def naive_string_match(text, pattern):
       n = len(text)
       m = len(pattern)
       for i in range(n - m + 1):
           j = 0
           while j < m and text[i + j] == pattern[j]:
               j += 1
           if j == m:
               print("Pattern found at index", i)

   text = "ABABDABACDABABCABAB"
   pattern = "ABABCABAB"
   naive_string_match(text, pattern)
   ```

7. **Numerical Algorithms**:

   a. Euclidean Algorithm:
   ```python
   def gcd(a, b):
       while b:
           a, b = b, a % b
       return a

   a, b = 60, 48
   print("GCD of", a, "and", b, "is", gcd(a, b))
   ```

8. **Probabilistic Algorithms**:

   a. Monte Carlo Simulation:
   ```python
   import random

   def monte_carlo_pi(num_samples):
       inside_circle = 0
       for _ in range(num_samples):
           x = random.uniform(-1, 1)
           y = random.uniform(-1, 1)
           if x**2 + y**2 <= 1:
               inside_circle += 1
       return (inside_circle / num_samples) * 4

   num_samples = 1000000
   print("Approximation of Pi using Monte Carlo Simulation:", monte_carlo_pi(num_samples))
   ```

These examples cover a range of common algorithms and demonstrate how to implement them in Python. Each example provides a function or code snippet along with a brief explanation of the algorithm it represents.