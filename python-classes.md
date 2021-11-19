## Python Classes
<a href="python">Back</a>

Also see:
- <a href="design-class">Tips for Designing a Class</a>
- <a href="inheritance">Inheritance and Composition</a>

Creating objects is the fundamental purpose of object oriented programming. Objects contain both data (data attributes) and procedures (methods). A class is code that specifies the data attributes and methods for a particular type of object.

### Name, Initializer Method, and Self Parameter

- **Class Names:** Class names are typically capitalized as a way to distinguish from variables.
- **Initializer Method:** Most classes also include an initializer method (__init__) as the first method of the class. The __init__ method initializes the object's data attributes and is automatically executed when an instance of the class is created in memory.
- **Self Parameter:** The self parameter provides a way for the method to know which object's data attributes its supposed to opperate on.

```python
class Coin
    def __init__(self):
        self.sideup = 'Heads'
```
In this example, when the object is created in memory that refers to this class, the __init__ method executes and the self parameter is automatically assigned the object that was just created. self.sideup = 'Heads' assigns the string 'Heads' to the sideup data attribute belonging to the object that was just created. This means that every object we create from the Coin class will initially have a sideup attribute that is set to 'Heads'.

### Attributes, Mutators, and Accessors
- **Attributes:** Attributes are identified in the initializer method, including self and the additional arguments provided.
- **Mutators:** Mutators are only needed if attribute will be changed during the program execution. These are the "set" methods.
- **Accessors:** Accessors allow you to return attribute values. These are the "get" methods.
- **String Method:** The string method can be used to display information when the print function is called. Basically, this method returns the object's state as a string.

```python
class PersonalInfo: # class name
    
    # Initializes the attributes.
    def __init__(self,name,address,age): # include self in the attributes and arguments
        self.__name = name
        self.__address = address
        self.__age = age
    
    # mutators (the set methods).
    def set_name(self, name): # "name" argument comes from the file where set_name is being called.
        self.__name = name
    
    def set_address(self, address): # "address" argument comes from the file where set_address is being called.
        self.__address = address

    def set_age(self, age): # "age" argument comes from the file where set_age is being called.
        self.__age = age

    # accessors (the get methods).
    def get_name(self):
        return self.__name
    
    def get_address(self):
        return self.__address

    def get_age(self):
        return self.__age

    # string method.
    def __str__(self):
        return "Name: " + self.__name + \
            "\nAddress: " + self.__animal_type + \
                "\nAge: " + self.__age
```

The PersonalInfo class would then be called into a program file that might look something like this:
```python
import filename

    # Variables created for attribute data:
    name = input('Please enter your name: ')
    address = input('Please enter your address: ')
    age = input('Please enter your age: ')

    # Create class instance for info and assign values to attributes.
    info = filename.PersonalInfo(name, address, age)

    # Use mutator methods to change information.
    name = input('Please enter the new name: ')
    info.set_name(name)

    # Accessor methods get this information and display it individually.
    print(info.get_name())
    print(info.get_address())
    print(info.get_age())
    # or use string method on object to display all information at once.
    print(info)
```