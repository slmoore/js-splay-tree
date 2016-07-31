#JavaScript Splay Tree

##Description:
  - A Splay Tree is a tree that rotates recently accessed nodes to the root.  
  - The root rotation process is known as "splaying".
  - **This implementation is restricted to Numbers and Strings only**
  - **This implementation does not allow duplicate keys**
  - splay-tree.js - version with full comments
  - splay-tree-clean.js - version with no comments
  - splay-tree.min.js - minified version
  - index.html - demo

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

####Usage
```
  //example helpers
  var nodes = '';
  var trace = function(node) {
      nodes += '{'+node.key + ' : ' + node.val + '} ';
  }
  var rootNow = function() {
      console.log( 'root now: '  + splayTree.root.key );
  }
  var minNow = function() {
      console.log( 'min: '+ splayTree.min().key +' : '+ splayTree.min().val );
  }
  var maxNow = function() {
      console.log( 'max: '+ splayTree.max().key +' : '+ splayTree.max().val );
  }

  //create
  var splayTree = new SplayBst();
  
  //insert and see root change
  splayTree.insert(14409,'Mount Rainier');
  rootNow();
  
  splayTree.insert(7979,'Mount Olympus');
  rootNow();
  
  splayTree.insert(4167,'Mount Si');
  rootNow();
  
  splayTree.insert(10781,'Mount Baker');
  rootNow();

  //min and max
  minNow();
  maxNow();

  //traverse
  splayTree.inOrder(splayTree.root, trace);
  console.log('inorder traversal ' + nodes);

  //remove and see root change
  splayTree.remove(4167);
  rootNow();
```

####Original Binary Search Tree structure modeled after Java implementation by:
  - Robert Sedgewick
  - algs4.cs.princeton.edu/code/edu/princeton/cs/algs4/BST.java

####Splay Tree Operations modeled after Java implementation by:
  - Josh Israel
  - algs4.cs.princeton.edu/33balanced/SplayBst.java

####Good References:
  - [http://cs.brynmawr.edu/Courses/cs206/fall2012/slides/09_SplayTrees.pdf](http://cs.brynmawr.edu/Courses/cs206/fall2012/slides/09_SplayTrees.pdf)
  - [http://courses.cs.washington.edu/courses/cse326/01au/lectures/SplayTrees.ppt](http://courses.cs.washington.edu/courses/cse326/01au/lectures/SplayTrees.ppt)