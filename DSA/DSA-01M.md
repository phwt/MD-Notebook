# Data Structure and Algorithms

## Data
- **Atomic Data** | `Integer`, `Char`, `Boolean`, etc.
- **Composite Data** | Student ID - 61070000 (YEAR-FACULTY-NUMBER), _Structured Data (`String`, `Array`, `File`)_

## Data Type
- **ADT** | Abstract Data Type - Data Structure Concept
- **Data Structure** | ADT Implementation
  - Types | Tree, Graph
  - Operations | Read, Search, Insert, Delete

## Linear List
- **Array** | Fixed (Static Memory Allocation - *On compile*)
  - Pros | No Pointer, Fast Indexing
  - Cons | Fixed Size, Single Data Type
- **Linked List** | Flexible (Dynamic Memory Allocation - *When running*)
  - Pros | Flexible Size
  - Cons | Have Pointer (Slower)
  - Types | Singly, Doubly
  
## Create List
- **Head Node** | Metadata `[Count, Head]`
- **Data Node** | Data `[Value, Next]`

## Stack
- LIFO Linear List
- **Operations**
  - `Push`
  - `Pop`
  - `Stack Top`
- **Application**
  - Reverse Data
  - Parsing Data | Parenthesis, Infix-Postfix
  - Backtracking | Four Queens Problem
  
## Queue
- FIFO
- **Operations**
  - `Enqueue`
  - `Dequeue`
  - `Queue Front`
  - `Queue Rear`

## Tree
- Root
- Parent
- Child
- Sibling
- Leaf
- Ancestor
- Descendent
- Degree | Child(s) count
- Level | *Start `0`*
- Depth | *Start `1`*
- Subtree | Branch(es) count
- Internal Nodes

## Binary Tree
- Has *at most* **two childs**
- **Types**
  - Complete Tree | Every level is filled
  - Nearly Complete Tree | Become complete without last level
- **Traversals**
  - Breadth-first | L-to-R
  - Depth-first
    - Preorder | Root-L-R
    - Inorder | L-Root-R
    - Postorder | L-R-Root
    
## Binary Search Tree
- L-Subtree < Root <= R-Subtree
- **Operations**
  - Traversals | Inorder = Sequential
  - Search | Start at `root` > Compare L-R > Repeat until found
  - Insertion | Compare until in condition
  - Delete
    - No child | Just delete
    - One subtree | Replace with subtree's root
    - Both subtree | Replace with left-subtree's highest
    
## Binary Expression Tree
- **Leaf node** | Operand
- **Root/Internal** | Operator
- **Subtree** | Subexpression
- **Traversals**
  - Preorder
  - Inorder | Open/Close parentheses on *Operator*
  - Postorder
  
## AVL Tree
- Self-balancing BST
  - Weight \[-1, 0, 1]
  - Balance Factor = `L-Subtree Height` - `R-Subtree Height`
- **Balancing**
  - `L-to-L` - Left-heavy > Rotate Right
  - `R-to-R` - Right-heavy > Rotate Left
  - `R-to-L` - Rotate Left then Right
  - `L-to-R` - Rotate Right then Left
- **Insertion** | Same as BST but with balancing

## Huffman Tree
- **Huffman Code** | Most common use fewer bits - Using ASCII = `Length` * `8`
- **Huffman Tree** | Order from *most common* to *least common* > Forming a subtree with the least common pair > Repeat

## Heap
- Complete / Nearly Complete Binary Tree
- **Types**
  - Max-heap | Child nodes <= Root
  - Min-heap | Child modes >= Root
- **Operations**
  - Reheap Up | *Insertion* - Compare with parent then swap
  - Reheap Down | *Deletion* - Compare with highest child then swap
- **Building** | Using Array
  - Build/Insert | Insert at the end of the heap then *reheap up*
  - Delete | Replace root with the last item in heap then *reheap down*
