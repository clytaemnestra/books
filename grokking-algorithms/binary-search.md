## Pseudocode
```
A = sorted array 
n = length of array 
x = value to be searched 

set low = 0
set high = n - 1

while x not found:
    mid = high - low // 2
    
    if x = A[mid]   
        EXIT: x found at location A[mid]
       
    if x > A[mid]
        low = mid + 1
       
    if x < A[mid]
        high = mid - 1 
      
end while
```
## Code
```python
def search(numbers_list, guess):
    low = 0
    high = len(numbers_list) - 1

    while low <= high:
        mid = (low + high) // 2

        if guess == numbers_list[mid]:
            return print("found the item: ", numbers_list[mid])

        elif guess > numbers_list[mid]:
            low = numbers_list[mid] + 1

        elif guess < numbers_list[mid]:
            high = numbers_list[mid] - 1

    return None


search(numbers_list=[1, 2, 3, 4, 5, 6, 7, 8, 9, 10], guess=8)

```