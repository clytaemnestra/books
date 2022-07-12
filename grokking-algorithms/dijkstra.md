## Principle
* terminology:
    * weight - number associate to every edge, makes weighted graph
    * undirected graph - both nodes point to each other, a cycle
* Dijkstra works only with directs acyclic grapgs (DAG)
* Dijkstra works when all weights are positive - if they're negative, use Bellman-Ford algorithm

### Pseudocode
* find the cheapest node (the node you can get in the least amount of time)
* update the costs of the neigbvors of this node
* repeat until you've done this for every node in the graph
* calculate the final path


### Code
```python
def find_lowest_cost_node(costs):
    lowest_cost = float(“inf”)
    lowest_cost_node = None
    for node in costs: # go through each node
        cost = costs[node]
        if cost < lowest_cost and node not in processed: # if it's the lowest so far and hasn't been processed
            lowest_cost = cost # set it as the new lowest-cost node.
            lowest_cost_node = node
    return lowest_cost_node

node = find_lowest_cost_node(costs) 
while node is not None:
    cost = costs[node]
    neighbors = graph[node]
    for n in neighbors.keys(): # go through the neighbours of this node
        new_cost = cost + neighbors[n] 
        if costs[n] > new_cost: # if it's cheaper to get to this neighbour by going through this node
            costs[n] = new_cost # update the cost for this node
            parents[n] = node # this node becomes the new parent for this neighbour
    processed.append(node) # mark the node as processed 
    node = find_lowest_cost_node(costs) # find the next node to process and loop 
```