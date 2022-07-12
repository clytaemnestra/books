## Principle
* used to answer the following 2 questions:
    * is there a path from node A to node B? 
    * what is the shortest path from node A to node B?
* running time: O(V+E) - number of vertices + number of edges 
* once you check an edge, make sure not to check it again - otherwise you might end up in an infinite loop

![image](https://user-images.githubusercontent.com/38294198/178215601-fa82ad9a-1315-49eb-9424-cc00dc81dd02.png)


### Pseudocode
* create a queue Q 
* mark v as visited and put v into Q 
* while Q is non-empty 
    * remove the head u of Q 
    * mark and enqueue all (unvisited) neighbours of u

![image](https://user-images.githubusercontent.com/38294198/178245559-f5dd169a-0efa-41aa-8e56-72decf862c3f.png)
![image](https://user-images.githubusercontent.com/38294198/178245596-5a37a33b-918d-439b-a428-5068e86e8483.png)
![image](https://user-images.githubusercontent.com/38294198/178245628-661d1909-d37e-4c81-8817-6bfacb7b834e.png)
![image](https://user-images.githubusercontent.com/38294198/178245652-bff1417b-0795-4da7-bbb3-50607043ad4d.png)
![image](https://user-images.githubusercontent.com/38294198/178245679-a88ececa-8ff6-471f-9b8a-c266a6e74466.png)
![image](https://user-images.githubusercontent.com/38294198/178245713-deb054a1-c391-4760-9005-f8d37f056518.png)


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

