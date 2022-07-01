## Principle
* figure out the base case - > very often it's an array with 0 or 1 element
* more closer to an empty array, reduce the size by using recursion


## Steps
* pick an element (pivot) from the array  
* find elements smaller than the pivot and the elements larger than the pivot - partitioning
* call quicksort on both sub-arrays  
* if sub-arrays are sorted, then you can combine the whole thing like left array + pivot + right array

## Code
```python
def quicksort(array):
    if len(array) < 2:
        return array

    else:
        pivot = array[0]
        left_array = [i for i in array[1:] if i <= pivot]
        right_array = [i for i in array[1:] if i > pivot]
    
    return quicksort(left_array) + [pivot] + quicksort(right_array)
```