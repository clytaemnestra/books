## Principle
![obrazek](https://user-images.githubusercontent.com/38294198/177056909-d7b57771-efb4-4055-8f20-644736deb9c9.png)

### Performance
![obrazek](https://user-images.githubusercontent.com/38294198/177056899-15f3fb0e-23f4-4edb-87aa-217dae1d2a7e.png)

### Colisions
* the simplest way: if multiple keys map to the same slot, start a linked list at that slot
* Python uses open addressing:
    * linear probing - if collision occurs, find the next slot 
    * quadratic probing - find the next slot + x*x

Linear probing:
```
If slot hash(x) % S is full, then we try (hash(x) + 1) % S
If (hash(x) + 1) % S is also full, then we try (hash(x) + 2) % S
If (hash(x) + 2) % S is also full, then we try (hash(x) + 3) % S 
```

Quadratic probing:
```
let hash(x) be the slot index computed using hash function.  
If slot hash(x) % S is full, then we try (hash(x) + 1*1) % S
If (hash(x) + 1*1) % S is also full, then we try (hash(x) + 2*2) % S
If (hash(x) + 2*2) % S is also full, then we try (hash(x) + 3*3) % S
```



### Operations principle
* insert(k): keep probing until an empty slot is found. Once an empty slot is found, insert k 
* search(k): keep probing until slot’s key doesn’t become equal to k or an empty slot is reached
* slots of deleted keys are marked specially as “deleted”, the insert can insert an item in a deleted slot, but the search doesn’t stop at a deleted slot

### Load factor
* measures how many empty slots remain in the hash table
* hashes use array for storage, so you count the number of occupied slots in an array, i.e. 2/5 = 0.4
* resize when your load factor is greater than 0.7 
