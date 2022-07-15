## Principle
* simple to write 
* get pretty close 
* NP-complete problems
    * hard to solve
    * better to use approximation algorithms 
    * example: travelling salesperson
* how to know if a problem is NP-complete:
    * algorithm slows down with more items
    * 'all combination of x' kind of problems
    * if you have to calculate every possible version of x, because you can't break it down into smaller subproblems
    * if it involves a set or sequence and it's hard to solve

### Example Problem
Suppose you’re starting a radio show. You want to reach listeners in all 50 states. You have to decide what stations to play on to reach all those listeners. 


It costs money to be on each station, so you’re trying to minimize the number of stations you play on. You have a list of stations. Each station covers a region, and there’s overlap.


How do you figure out the smallest set of stations you can play on to cover all 50 states? 

#### Greedy Algorithm Principle
1. Pick the station that covers the most states that haven’t been covered yet. It’s OK if the station covers some states that have been covered already. 
2. Repeat until all the states are covered.

#### Greedy Algorithm Code
```python

# You pass an array in, and it gets converted to a set.
states_needed = set(["mt", "wa", "or", "id", "nv", "ut", "ca", "az"])

stations = {}
stations["kone"] = set(["id", "nv", "ut"])
stations["ktwo"] = set(["wa", "id", "mt"])
stations["kthree"] = set(["or", "nv", "ca"])
stations["kfour"] = set(["nv", "ut"])
stations["kfive"] = set(["ca", "az"])

final_stations = set()

while states_needed:
  best_station = None
  states_covered = set()
  for station, states_for_station in stations.items():
    covered = states_needed & states_for_station
    if len(covered) > len(states_covered):
      best_station = station
      states_covered = covered

  states_needed -= states_covered
  final_stations.add(best_station)

print(final_stations)
```