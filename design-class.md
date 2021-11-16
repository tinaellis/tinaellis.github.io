## Techniques for Designing Classes
<a href="python">Back</a>

### Steps for Designing Classes
1 - Find the Classes in the problem:
- Get a written description of problem domain
- Identify the nouns
- Refine the list to only classes relavant to the problem

2 - Identify the Class's Responsibility:
- Attributes: The things the class is responsible for knowing
- Methods: The things the class is responsible for doing

3 - Design a UML Diagram
Unified modeling language (UML) diagram:
    # TOP: Name of class
    # MIDDLE: List of class's attributes
    # BOTTOM: List of class's methods

## Example
### Attributes and Methods Identified and Separated
- What must the class know (attributes):
    -- customer name
    -- customer address
    -- customer phone

- What must the class do (methods):
    -- initialize an object
    -- set and return name
    -- set and return address
    -- set and return phone

### Create UML Diagram
```python
------------------------------
        Customer                # class name
------------------------------
__name
__address
__phone                         # class attributes
------------------------------
__init__(name, address, phone)
set_name(name)
set_address(address)
set_phone(phone)
get_name(name)
get_address(address)
get_phone(phone)                # class methods
------------------------------
```
### Translate Information into Class
```python
class Customer:
    def __init__(self, name, address, phone):
        self.__name = name
        self.__address = address
        self.__phone = phone

    def set_name(self, name):
        self.__name = name

    def set_address(self, address):
        self.__address = address

    def set_phone(self, phone):
        self.__phone = phone

    def get_name(self):
        return self.__name

    def get_address(self):
        return self.__address

    def get_phone(self):
        return self.__phone
```