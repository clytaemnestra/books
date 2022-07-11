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
graph = {
    'A': ['B', 'C'],
    'B' : ['D', 'E'],
    'C' : ['F'],
    'D' : [],
    'E' : ['F'],
    'F' : []    
}

visited = [] # keep track of visited nodes
queue= [] # initialize a queue to add neighbours

def bfs(visited, graph, node):
    visited.append(node)
    queue.append(node)

    while queue:
        s = queue.pop(0) # first node in the queue
        print(s, end = " ")

        for neighbour in graph[s]:
            if neighbour not in visited:
                visited.append(neighbour)
                queue.append(neighbour)

# driver code
bfs(visited, graph, 'A')
```

