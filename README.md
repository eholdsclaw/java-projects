# SplayTree
Data Structures Assignment for Splay Implementation in Java

Binary Search Tree code from other Data Structures assignment augmented with splay method.

  Interface: The SPLT will provide these operations:

  insert:
    
    in: a string (the element to be stored into the tree)
   
    return: void
   
    effect: 
    
            - if the string is already in the tree, then there is no change to
              the tree state (save for splaying), and return
            - if the string is not already in the tree, then a new tree cell/node
              is created, the string put into it as data, the new node is linked
              into the tree at the proper place; size is incremented by 1,
              and return
              
 remove:
  
    in: a string (the element to be taken out of the tree)
   
    return: void
   
    effect:
    
            - do "contains" on node to be removed, which splays the node to the root if it is in the tree; if it is not in the tree, the "contains" splays the last accessed node to the root
            - root node is unhooked; left with two subtrees: the left and right child
            - do "findMax" on left child, which splays max to the root and the new root of left child with no right subtree
            - the right child is made the right child of the left subtree
    
 contains:
   
    in: a string (the element to be searched for)
   
    return: boolean 
            
            - if the tree contains the string being searched for then return true; else return false
            - (this means return false if tree size is 0)
    effect: no change to the state of the tree (except for splaying found node or what would be the parent of that node)

 findMin:
  
    in: none
   
    return: string, the smallest element value from the tree
   
    effect: no tree state change (except for splaying)
   
    error: if tree size is 0, then return null


 findMax:
   
    in: none
   
    return: string, the element value from the tree that is largest
   
    effect: no tree state change (except for splaying)
   
    error: if tree size is 0, then return null

 size:
   
    in: nothing
   
    return: number of elements stored in the tree
   
    effect: no change to tree state

 empty:
   
    in: nothing
   
    return: boolean
           
           - if the tree has no elements in it then return true, else return false
    effect: no change to tree state

 height:
   
    in: none
   
    return: integer
         
         - (the length of the longest path in the tree from root to a leaf)
    effect: no change in tree state
    error: if the tree is empty, return -1 (also, if size is 0, root is null)

 getRoot:
    
    in: none
    
    return: a tree cell/node, the one that is the root of the entire tree
            means return a null if the tree is empty
    
    effect: no change to tree state
