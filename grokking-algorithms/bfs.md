## Principle
* used to answer the following 2 questions:
    * is there a path from node A to node B? 
    * what is the shortest path from node A to node B?
* running time: O(V+E) - number of vertices + number of edges 
* once you check an edge, make sure not to check it again - otherwise you might end up in an infinite loop

![image](https://user-images.githubusercontent.com/38294198/178215601-fa82ad9a-1315-49eb-9424-cc00dc81dd02.png)


### Pseudocode
* pick any node (mostly root), visit a neighbour, mark it as visited, print it and insert it in a queue
* remove the first vertex from the queue
* repear 1 and 2 until the queue is empty or the desired node is found

### Code
```python
import collections

def bfs(graph, root):
    visited, queue = set([root]), collections.deque([root])
    while queue:
        vertex = queue.popleft()
        visit(vertex)
        for node in graph[vertex]:
            if node not in visited:
                visited.add(node)
                queue.append(node)

def visit(n):
    print(n)

if __name__ == '__main__':
    graph = {0: [1, 2], 1: [2, 0], 2: []} 
    bfs(graph, 0)
```

