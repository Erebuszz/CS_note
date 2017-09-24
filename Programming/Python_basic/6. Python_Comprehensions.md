* noted by Erebuszz, modified on 5/14/2017

* Excerpts from << Python 101 >>

A couple of methods for creating lists and dictionaries

# List comprehensions

```python
x = [i for i in range(5)]
print(x)
```
Output

    [0, 1, 2, 3, 4]

## Used as a kind of filter

```python
the_str = "I have 2 big dogs!"

if [i for i in the_str if "1" or "2" or "3" in i]:
    print("I have big dogs!")
```
Output

    I have big dogs!

## Cast a bunch of strings into integers

### Wrong method

```python
x = ['1', '2', '3', '4', '5']
x = int(x)
print(x)
```
Output

    Traceback (most recent call last):
    File "/Users/erebus/Github/demo_project/demo.py", line 2, in <module>
        x = int(x)
    TypeError: int() argument must be a string or a number, not 'list'

### Right method

```python
x = ['1', '2', '3', '4', '5']
x = [int(i) for i in x]
print(x)
```
Output

    [1, 2, 3, 4, 5]

```python
str_list = [' one', '  two ', 'three', '  four  ', '   five    ']
x = [s.strip() for s in str_list]
print(x)
```
Output

    ['one', 'two', 'three', 'four', 'five']

## Flatten multiiple strings into one

```python
vec = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
the_list = [num for elem in vec for num in elem]
print(the_list)
```
Output

    [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Dictionary Comprehensions

> Start in Python 3 and back ported in Python 2.7

```python
the_dict = {i: str(i) for i in range(5)}
print(the_dict)
```
Output

    {0: '0', 1: '1', 2: '2', 3: '3', 4: '4'}

## Swap the keys and values

```python
one_dict = {"dog": 1, "cat": 2, "mouse": 3}
the_dict = {value: key for key, value in one_dict.items()}
print(the_dict)
```
Output

    {1: 'dog', 2: 'cat', 3: 'mouse'}

> This will only work if the dictionary values are <b>non-mutable</b> type

# Set Comprehensions

Create a normal set

```python
my_list = [1, 1, 3, 2, 3, 5, 8, 6, 5]
my_set = set(my_list)
print(my_set)
```
Output

    set([1, 2, 3, 5, 6, 8])

Use a set comprehension

```python
my_list = [1, 1, 3, 2, 3, 5, 8, 6, 5]
my_set = {x for x in my_list}
print(my_set)
```
Output

    set([1, 2, 3, 5, 6, 8])

Just basically change the square brackets that a list comprehension use to the curly braces that a dictionary comprehension has