**1.Static method:**
use when you want to denote method inside of a class as **static**.

**2.When to use:**
Static methods only belong to class, not to the instance of a class. means when you do not want to instantiate class, but want to access methods inside of them.

```Python
class MathOperations:
    @staticmethod
    def add(x, y):
        return x + y

    @staticmethod
    def subtract(x, y):
        return x - y

# You can call static methods directly on the class without needing to instantiate an object
print(MathOperations.add(5, 3))  # Output: 8
print(MathOperations.subtract(5, 3))  # Output: 2

```