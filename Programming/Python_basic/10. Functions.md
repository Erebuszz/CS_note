* noted by Erebuszz, modified on 6/7/2017

* Excerpts from << Python 101 >>

A block of code that starts with the <b>def</b> keyword

# An Empty Function (the stub)

```python
def empty_function():
    pass
```

The <b>pass</b> statement is normally a null operation, which means nothing happens

# Passing Arguments to a Function

```python
def add(a, b):
    return a + b

print("1 + 3 = %d" % add(1, 3))
```
Output

    1 + 3 = 4

Note that you can also call the function by passing the name of the arguments

```python
add(b=1, a=3)
```

# Keyword Arguments

Set the default values

```python
def add(a=1, b=3):
    return a + b

print(add(5, 4))
print(add())
```
Output

    9
    4

Mix the normal usage with keyword arguments

```python
def add(a, b=3, c=4):
    return a + b + c

print(add(1))
print(add(1, b=2, c=3))
```
Output

    8
    6

# *args and **kwargs

args for infinite arguments

kwargs for infinite keyword arguments

* The naming of the arguments are just convention

```
>>> def many(*args, **kwargs):
...     print(args)
...     print(kwargs)
...
>>> many(1, 2, 3, name="Mike", job="programmer")
(1, 2, 3)
{'name': 'Mike', 'job': 'programmer'}
```

# A Note on Scope and Globals

If we define the variables inside of a function, those variables can only be used inside that function

```python
def function_a():
    a = 1
    b = 2
    return a+b

def function_b():
    c = 3
    return a+c

print(function_a())
print(function_b())
```
You will receive the following error
```
NameError: global name 'a' is not defined
```

Get around this by telling Python that a is a global variable
```python
def function_a():
    global a = 1
    b = 2
    return a+b

def function_b():
    c = 3
    return a+c

print(function_a())
print(function_b())
```

