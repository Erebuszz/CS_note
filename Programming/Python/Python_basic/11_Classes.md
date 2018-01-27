* Excerpts from << Python 101 >>

- Everything in Python is an object
    - What this means is that every thing in Python has methods and values. The reason is that everything is based on a class

# Creating the class

```python
# python 2.x syntax
class Vehicle(object):
    """docstring"""

    def __init__(self):
        """constructor"""
        pass

# python 3.x syntax
# In Python 3, we don't need to explicitly say we're inheriting from object
class Vehicle:
    """docstring"""

    def __init__(self):
        """constructor"""
        pass
```
- In Python, convention says that the class name should have the first letter <b>capitalized</b>
- The <b>object</b> is what the class is based on or inheriting from, known as the base class or parent class
- \_\_init\_\_
    - for initialization
    - only called once inside the program

> A function changes its name to "method" when it is within a class

# What is self

- A way to tell one instance from another

```python
class Vehicle:

    def __init__(self, color, vtype):
        """Constructor"""
        self.color = color
        self.vtype = vtype

    def brake(self):
        """
        stop the car
        """
        return "%s braking" % self.vtype

    def drive(self):
        """
        drive the car
        """
        return "I'm driving a %s %s" % (self.color, self.vtype)


# only run the following code if this code is executed as a standalone file
if __name__ == "__main__":
    car = Vehicle("blue", "car")
    print(car.brake())
    print(car.drive())
    truck = Vehicle("red", "truck")
    print(truck.drive())
    print(truck.brake())
```

    car braking
    I'm driving a blue car
    I'm driving a red truck
    truck braking

In this code, you create two instances (car, truck)

- Each instance has its attributes and methods

# Subclasses

We've already created a subclass when created a class based on object

```python
class Car(Vehicle):
    """
    The car class
    """
    def brake(self):
        """
        Overide brake method
        """
        return "The car class is breaking slowly"

if __name__ == "__main__":
    car = Car("blue", "car")
    print(car.brake())
    print(car.drive())
```

    The car class is breaking slowly
    I'm driving a blue car

When you subclass Vehicle, you get all its attributes and methods unless you override them