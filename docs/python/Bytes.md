1. Varibale Casing

Casing in python:
Pascal casing is not used in python much.
![Alt text](image.png)

2. **id()**: unique identifier is memory address of object referenced by a variable. 
```python
a = 10000
id1 = id(a)
b = a + 2-2
id2 = id(b)

print(id1)
print(id2)
```

3. `and` VS `or`:
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

4. If any problem is related to *Arrays* & it involves o(n^2) time complexity, then doing a computation that takes O(log n) wont make much difference. So Overall time complxity will again be O(n^2) only. here it is *Sorting* the array that takes O(log n). 


5. Anonymous Variable.

```Python
for _ in range(100): # here instead of "i", "_" is used. so we are limiting memory & usage.
    print("This is Bytes of Python")

a,b,_ = "value1", "value2", "value3" # since we dont need "value3" to use, so using anonymous variable.
```

6. Function readability:

Instead of keeping multiple logics in Single function, it is always better to keep multiple simple functions for multiple logics. this way it is easier to route through, to understand, to read the code more clearly.

7. Type hinting:

Type hinting in python enhances code readability. helps anyone to easily understand the type of data that goes inside and comes outside of a function.
