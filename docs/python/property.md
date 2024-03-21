**1.Private variable:**
Like in Other programming languages, python also has *private variable* option. Any variable that has "_" before the name of variable is called *private variable*.

ex: `_my_attribute`

**2.Property:**
Using `@property` **decorator**, we can access those *private variables* even outside of the Class. 


**3.getter:**
using `@propery` on top of any method, default becomes "Getter method".

**4.Setter:**
using `@method.setter` functionality on top of a function, gives access to set a value to the *private variable*.

##### Example

```Python
class MyClass:
    def __init__(self):
        self._my_attribute = None  # Private attribute with leading underscore convention
    
    # Getter method
    @property
    def my_attribute(self):
        return self._my_attribute
    
    # Setter method
    @my_attribute.setter
    def my_attribute(self, value):
        self._my_attribute = value

    # delter method
    @my_attribute.deleter
    def my_attribute(self,):
        print("Deleted")
        del self._my_attribute

# Usage
obj = MyClass()
obj.my_attribute = 42  # Calls the setter method
print(obj.my_attribute)  # Calls the getter method
del obj.my_attribute # deletes the variable.
```
