### Binary Search Tree 
![image](https://user-images.githubusercontent.com/38294198/179522822-56fdf0c4-2622-4625-b7a0-e8ee14058783.png)
* cons - don't have random access 
* performance times are on average and rely on the tree being balanced

Unbalanced tree:
![image](https://user-images.githubusercontent.com/38294198/179523066-8eac29b8-1b84-4829-8da0-0420f0080cd8.png)

### B-Trees
* self-balancing search tree
* time complexity of all operations is O(log n)
* insertion happens only at leaf node
* shrinks from the root (binary search tree grows downward and also shrinks from downward)
![image](https://user-images.githubusercontent.com/38294198/179523576-fe09d4e2-a061-45ca-ac19-59ecb8f30238.png)


### Red-black trees
* self-balancing binary search tree
* search time - O(log n)
* every node has an extra bit, which is either red or black - used for balance
* 1 bit to store the colour information, identical memory footprints to the classic binary search tree
* root is always black
* a red node cannot have a red parent or red child
* every path from a node (including root) to any of its descendants NULL nodes has the same number of black nodes
* all leaf nodes are black nodes 
* used in KNN for reducing time complexity
* MySQL uses B+ trees fot data indexing in database engine


### Heaps
* similar to the binary tree with the difference that heap has in the root either minimum or maximum values
* it's possible to have duplicates in heap
