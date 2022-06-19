
## Pseudokód
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