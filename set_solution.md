## Solution:

```python
#Create a function for Union
def union(set1, set2):
    
    set3 = {i for j in (set1, set2) for i in j}
    
    return set3

#Create a function for Intersection 
def intersection(set1, set2):

    set3 = {i for i in set1 if i in set2}

    return set3

set1 = {1,2,3,4,5,6}        
set2 = {4,5,6,7,8,9}        
print(union(set1, set2))            #{1, 2, 3, 4, 5, 6, 7, 8, 9}
print(intersection(set1, set2))     #{4, 5, 6}

set1 = {1,3,5,7,9}          
set2 = {2,4,6,8,10}         
print(union(set1, set2))            #{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
print(intersection(set1, set2))     #set()  Empty set
```

Back to Sets: [Sets](sets.md)