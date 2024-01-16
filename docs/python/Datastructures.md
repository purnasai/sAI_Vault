This has all the python course it needs.

It has 4 modules:

- Data structures: For Basic python
- OOPS: For Classes and Functions in python
- Algorithms: For Search, Sort and Other algorithms
- Bytes: Quick points to Excel

<!-- NOTE: All of the Notes here has Github links.

websites used: 
- https://stackabuse.com/linear-search-in-python/
- Real python
- https://note.nkmk.me/en/
- check others from Notion -->

## Data Structures:

1. Max Number: Finding the Max number in a list
```python
# problem: Largest of N numbers
# solution: we can use a for loop, iterate over & compare.
numbers = [23,45,56,44,56,77,33,44,22,11,10]

big = numbers[0] 
# it is advantage to take the ""First value"" in list, rather than taking big = np.inf
# or big = 0

for number in numbers:
    if number>big:
        big = number

print(big)
```

2. GCD or HCF: Finding the Max Common number that devides the numbers.
```python
# Problem: find GCD (or) HCF
# Solution: get common max number, start dividing from 1st table.
a = 30
b = 25

big = 1 # starting with 1st table
for i in range(1, max(a,b)): # iterating till to the max value of both vals, to get common number.
    if a%i == 0 and b%i == 0:
        if i>big:
            big = i

print(big)
```

3. Proper use of `if` vs `elif`:
```python
button = int(input())

while button != 6:
    if button <= 5 and button>=1: # since it is b/n 2 bounds, "AND" is used.
        a = int(input())
        b = int(input())
    if button ==1:
        print(a+b)
    if button ==2:
        print(a-b)
    if button ==3:
        print(a*b)
    if button ==4:
        print(a//b)
    if button ==5:
        print(a%b)
    elif button <1 or button >5: # Since it is outside of 2 bounds, "OR" is used.
        print("Invalid Operation")
    button = int(input())
```

4. Fibanocci number: Fibanocci is a number pattern that use its precident 2 numbers and keeps their sum as 3 rd number. There are many different ways. this is one way.
```python
N = 20
n1 = 1
n2 = 2

summ = n1+n2
flag = True
while flag:
    if summ < N:
        print(summ)
        summ = n1+n2
        n1 = n2
        n2 = summ
    else:
        flag = False
```


5. Reverse Number
```python
num = 1234
reversed_num = 0

while num != 0:
    digit = num % 10 # it gives the remainder. Always last value in a number from right side.
    reversed_num = reversed_num * 10 + digit # this increases number at 10X & adds Remainder. 
    num //= 10 # this gives the quotient with roundedness.
    
print("Reversed Number: " + str(reversed_num))
```

6. Palindrome Number: If Reverse of a number equal to the number, then it is palindrome. ex: `121`
```python
n=int(input())  

def check_palindrome(n):
    reverse = 0
    start = n
    while n:
        remainder = n%10
        reverse = (reverse*10) + remainder
        n = n//10

    if start == reverse:
        print("true")
    else:
        print("false")

check_palindrome(n)
```