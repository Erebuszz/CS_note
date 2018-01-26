* noted by Erebuszz, modified on 5/9/2017

* Excerpts from << Python 101 >>

# Lists

## Create empty lists

```python
my_list = []
my_list = list()
```

A list contains a list of elements, such as strings, integers, objects or a mixture of types

```python
my_list = [1, 2, 3]
my_list1 = ["a", "b", "c"]
my_list2 = [1, "d", 3]
```

## Create lists of list

    >>> my_nested_list = [my_list1, my_list2]
    >>> my_nested_list
    [[1, 2, 3], ['a', 'b', 'c']]

## Combine two lists together

### Use the extend method

    >>> target_list = [1, 2, 3]
    >>> a_list = [7, 8, 9]
    >>> target_list.extend(a_list)
    >>> target_list
    [1, 2, 3, 7, 8, 9]

### Add two lists together (easier way)

    >>> target_list = [1, 2, 3]
    >>> a_list = [7, 8, 9]
    >>> target_list += a_list   # a += b is equal to a = a + b
    >>> target_list
    [1, 2, 3, 7, 8, 9]

### extend vs append

append: Appends object at end.

    x = [1, 2, 3]
    x.append([4, 5])
    print (x)

gives you: [1, 2, 3, [4, 5]]

extend: Extends list by appending elements from the iterable.

    x = [1, 2, 3]
    x.extend([4, 5])
    print (x)

gives you: [1, 2, 3, 4, 5]

## Sort a list

    >>> the_list = [22, 14, 55, 73, 32, 80, -23]
    >>> the_list.sort()
    >>> the_list
    [-23, 14, 22, 32, 55, 73, 80]

### Wrong method

    >>> the_list = [22, 14, 55, 73, 32, 80, -23]
    >>> target_list = the_list.sort()
    >>> target_list
    >>> print(target_list)
    None

## Slice a list just like you do with the string

    >>> the_list[:3]
    [-23, 14, 22]

## Remove elements from a list

### Use the remove() method
    
    >>> list1 = ["I", "am", "not", "the", "hero"]
    >>> list1
    ['I', 'am', 'not', 'the', 'hero']
    >>> list1.remove("not")
    >>> list1
    ['I', 'am', 'the', 'hero']

### Pop from the end

    >>> my_list = [1, 2, 3, 4, 5]
    >>> my_list.pop()
    5
    >>> my_list
    [1, 2, 3, 4]

# Tuples

> A tuple is immutable while a list is mutable

## Create a tuple

    >>> my_tuple = (1, 2, 3, 4, 5)
    >>> my_tuple.sort()
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    AttributeError: 'tuple' object has no attribute 'sort'

### Use the tuple() method

```python
the_tuple = tuple()
one_tuple = tuple([1, 2, 3])    # An example of casting
```

You can also turn the tuple back into list

```python
the_list = list(one_tuple)
```

# Dictionaries

> A dictionary is an <b>unordered</b> set of <b>key:value</b>

* A list cannot be used as a key

## Create a dictionary

    >>> my_dict = {}
    >>> the_dict = dict()

    >>> one_dict = {"name": "Tom", "gender": "Man", "phone": "123"}
    >>> one_dict
    {'phone': '123', 'name': 'Tom', 'gender': 'Man'}

## Access a value

    >>> one_dict["name"]
    'Tom'

## Tell if a key is in a dictionary

    >>> "gender" in one_dict
    True
    >>> "hobby" in one_dict
    False

## Get a listing of all the keys

    >>> one_dict.keys()
    dict_keys(['phone', 'name', 'gender'])

### <b>in</b> method comparison

```python
"gender" in one_dict        # this is good
"gender" in one_dict.keys() # this works too, but is slower
```