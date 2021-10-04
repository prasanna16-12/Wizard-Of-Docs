# ⭐ Preorder Tree Traversal (Root☝ -> Left👈 -> Right👉)
In computer science, tree traversal (also known as tree search and walking the tree) is a form of graph traversal and refers to the process of visiting (e.g. retrieving, updating, or deleting) each node in a tree data structure, exactly once. Such traversals are classified by the order in which the nodes are visited. The following algorithms are described for a binary tree, but they may be generalized to other trees as well.
#### Example: 
##### Input: `root node` *(Pointer)* 
##### Output: ` F, B, A, D, C, E, G, I, H `
##### Explanation: 
### Consider structure of Tree Node for clear understanding
##### Node consist of value and pointer to its left and right child
```py
class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data
```


![tree](https://upload.wikimedia.org/wikipedia/commons/7/75/Sorted_binary_tree_ALL_RGB.svg)<br/>
- Visit the current node (in the figure: position red).
- Recursively traverse the current node's left subtree.
- Recursively traverse the current node's right subtree.

> #### Recursive
### Pseudo Code
``` js
procedure preorder(node)
    // if no node then backtrack
    if node = null
        return
    
    visit(node)
    preorder(node.left)
    preorder(node.right)
```
### Code `Python`
``` py
def preorder(root):
  if not root:
    return 
  
  print(root.data)
  preorder(root.left)
  preorder(root.right)
```
> #### Iterative
### Pseudo Code
``` js
procedure iterativePreorder(node)
    if node = null
        return
    stack ← empty stack
    stack.push(node)
    while not stack.isEmpty()
        node ← stack.pop()
        visit(node)
        // right child is pushed first so that left is processed first
        if node.right ≠ null
            stack.push(node.right)
        if node.left ≠ null
            stack.push(node.left)
```
### Code `Python`
``` py
def iterativePreorder(root):
  if not root:
    return
  stack = []
  stack.append(root)
  while len(stack):
    temp = stack.pop()
    print(temp.data)
    # right child is pushed first so that left is processed first
    if temp.right:
      stack.append(temp.right)
    if temp.left:
      stack.append(temp.left)       
```

#### ⏲️ Time Complexities:
`O(n)`  *As we are visiting every node* 
<br/>
#### 👾 Space complexities:
`O(n)`  *recursion stack space*
