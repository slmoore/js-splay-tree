#JavaScript Splay Tree

##Description:
  - A Splay Tree is a tree that rotates recently accessed nodes to the root.  
  - The root rotation process is known as "splaying".
  - **This implementation is restricted to Numbers and Strings only**
  - **This implementation does not allow duplicate keys**

##See it in action:
  - [Splay Tree Visualizer](http://slmoore.github.io/SplayTreeVisualizer/)
  - [Visualizer Source Code](https://github.com/slmoore/SplayTreeVisualizer)

##Purpose:
  - Popular nodes will be quicker and more efficiently accessed.  
  - If a tree contains many nodes, but only a small percentage are regularly used, 
  then it is more efficient to keep the recently accessed nodes closer to the root.

###Methods:
  - `search` - Returns the node with the given key or null.  Splays tree around key.
  - `insert` - Inserts new node at the root of the tree, or Replaces the value.  Splays tree around key.
  - `remove` - Removes node with the given key.  Splays tree around key and merges left/right subtrees.
  - `min` - Find the minimum node. No splay operation.
  - `max` - Find the maximum node. No splay operation.
  - `inOrder` - In Order traversal of the tree.  No splay operation.
  - `rotateRight` - Splay helper function. Rotate node to be the right child of it's current left child.
  - `rotateLeft` - Splay helper function. Rotate node to be the left child of it's current right child.
  - `splay` -  Splay operation moving the closest matching node to the root of the tree through Zig-Zag and Zig-Zig operations.

###Node properties:
  - `key` - key to identify where to locate the node.
  - `val` - data stored by the node.
  - `left` - Left child node.
  - `right` - Right child node.

####Original Binary Search Tree structure modeled after Java implementation by:
  - Robert Sedgewick
  - algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BST.java

####Splay Tree Operations modeled after Java implementation by:
  - Josh Israel
  - algs4.cs.princeton.edu/33balanced/SplayBst.java

####Good References:
  - [http://cs.brynmawr.edu/Courses/cs206/fall2012/slides/09_SplayTrees.pdf](http://cs.brynmawr.edu/Courses/cs206/fall2012/slides/09_SplayTrees.pdf)
  - [http://courses.cs.washington.edu/courses/cse326/01au/lectures/SplayTrees.ppt](http://courses.cs.washington.edu/courses/cse326/01au/lectures/SplayTrees.ppt)