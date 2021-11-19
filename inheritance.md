## Inheritance and Composition
<a href="python">Back</a>

### Inheritance
With inheritance, a child class inherits all of the attributes and methods from the parent class. Inheritance is referred to as a "is-a" relationship.

### Composition
Composition is a design model where an object knows another object and explicitly delegates some tasks to it. With composition, you control what is inherited from the parent class. Composition is referred to as a "has-a" relationship.

- Composition example <a href="https://trinket.io/python/4bf9efdc84?showInstructions=true" target="_blank">Rosie the Robot</a>

- Use composition when you can
- Use inheritance when you must

### Inheritance "is-a relationship" example
 ```python
class Animal():
    def eat(self):
        print('yum')

class Dog(Animal):
    def bark(self):
        print('Woof')

class Cat(Animal):
    def meow(self):
        print('Meow')
    
snoopy = Dog()
snoopy.bark()
snoopy.eat()
```

### Composition "has-a relationship" example
Here we made each skill a class and composed a new class by including objects from other classes.

```python
class Dog():
    def bark(self):
        print('Woof')
class Robot():
    def move(self):
        print('Ahh mobility..')
class CleanRobot():
    def clean(self):
        print('I vacuum dust')
class CookRobot():
    def cook(self):
        print('I make homemade pasta')

class Superbot():
    def __init__(self):
        # this class contains 3 objects.
        # Not using inheritance, we're using composition.
        self.o1 = Robot()
        self.o2 = Dog()
        self.o3 = CleanRobot()

    def playGame(self):
        print('Chess is best')
    
    # we still have to define these methods but we're calling them from the classes
    def move(self):
        return self.o1.move() 
    def bark(self):
        return self.o2.bark()
    def clean(self):
        return self.o3.clean()

henry = Superbot()
henry.move() # prints 'Ahh mobility'
henry.bark() # prints 'Woof'
henry.playGame() # prints 'chess is best'
```