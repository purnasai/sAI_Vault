https://realpython.com/introduction-to-python-generators/


Generators and more advanced concepts.

1. **id()**: unique identifier is memory address of object referenced by a variable. 
```python
a = 10000
id1 = id(a)
b = a + 2-2
id2 = id(b)

print(id1)
print(id2)
```

2. `and` VS `or`:
```python
# inclusive
if 5>0 and 5<10: # when the number is b/n 2 bounds
    print("Yes Condition true")
```
or 
```python
# Exlusive
s = 10
if 10 < 15 or 10> 0: # when the number is outside 2 bounds
    print("yes it is true")
```

3. If any problem is related to *Arrays* & it involves o(n^2) time complexity, then doing a computation that takes O(log n) wont make much difference. So Overall time complxity will again be O(n^2) only. here it is *Sorting* the array that takes O(log n). 