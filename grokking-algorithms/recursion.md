# Recursion
* every recursive function has two parts:
    * the base case - condition, when to stop the loop
    * the recursive case - when the function calls itself
* tail recursion 
    * tail - the last thing
    * tail recursion = recursion is the last thing that happens 
    * some compilers optimize the tail recursion - it's space complexity is O(n), sometimes it's better to use loops
  

### Example
Factorial calculation:
```python
def factorial(x):
    if x == 1:
        return 1
    else:
        return x * factorial(x-1)
```
fac n = n * fac (n - 1)

Example: 
fac 4 = 4 * fac3
      = 4 * (3 * fac2)
      = 4 * (3 * (2 * fac1))
      = 4 * (3 * (2 * 1))
      = 4 * (3 * 2)
      = 4 * 6
      = 24


Tail-recursive (takes number & variable, which accumulates factorials):
```python
def factorial(x, a = 1):
    if x == 1:
        return a
    return factorial(x - 1, x * a)
```
fac n = go n 1
go 1 a = a
go n a = go (n - 1)

Example: 
fac 4 = go 4 1
      = go (4 - 1) (1 * 4)
      = go 3 4
      = go 2 12
      = go 1 24
      = 24