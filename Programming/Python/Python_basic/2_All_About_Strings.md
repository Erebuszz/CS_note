* noted by Erebuszz, modified on 5/9/2017

* Excerpts from << Python 101 >>

# <font color="lightblue">Create a string</font>

You can use single , double or triple quotes one of three ways

```python
my_string = "Welcome to Python!"
another_string = 'Bla Bla Bla'
a_long_string = '''This is a 
multi-line string. It covers more than 
one line.'''
```

The triple quoted line can be done with 
three single quotes or three double quotes

You will noticed that 
output retains the line breaks if you print it out

## Use the <b>str</b> methods

```python
my_number = 123
my_string = str(my_number)
```

> Noted: string is one of Python <b>immutable</b> types

So, the following example will cause an error

```python
my_string = "abc"
my_string[0] = "d"
```

Every time we assign a new value to the variable, 
its identity changes

    >>> string = "abc"
    >>> id(string)
    4302870376
    >>> string = "sdf"
    >>> id(string)
    4324422576

> In Python 2.x, strings can only contain <b>ASCII</b> characters

## Precede your string with a <b>u</b> in Python 2.x for unicode

```python
my_unicode_string = u"This is a unicode!"
```

# <font color="lightblue">String Concatenation</font>

    >>> string_one = "My dog ate "
    >>> string_two = "my homework."
    >>> string_three = string_one + string_two
    >>> string_three
    'My dog ate my homework.'

# <font color="lightblue">String Methods</font>

> Everything in Python is an object

Strings have their own methods built into them, 
such as <b>upper()</b>

    >>> my_string = "abc"
    >>> my_string.upper()
    'ABC'

## Get a list of all the string methods:

    >>> dir(my_string)

To learn what the methods is for, 
just ask for <b>help()</b>

    >>> help(my_string.capitalize)
    Help on built-in function capitalize:

    capitalize(...) method of builtins.str instance
        S.capitalize() -> str

        Return a capitalized version of S, i.e. make the first character
        have upper case and the rest lower case.

## Tell what type the variable is
    
    >>> type(my_string)
    <class 'str'>

# <font color="lightblue">String Slicing</font>

    >>> my_string = "I love Python!"
    >>> my_string[:1]
    'I'

> From the example we can see that this grabs the 1st character in the string up to, but <b>not</b> including the 2nd character.

## More examples : 

    >>> my_string[:13]
    'I love Python'
    >>> my_string[0:14]
    'I love Python!'
    >>> my_string[0:-1]
    'I love Python'
    >>> my_string[:]
    'I love Python!'
    >>> my_string[2:]
    'love Python!'

# <font color="lightblue">String Formatting (AKA Substitution)</font>

## Old Way of Substituting Strings

    >>> my_string = "I love %s" % "Python"
    >>> my_string
    'I love Python'
    >>> var = "pizza"
    >>> my_string = "I hate %s" % var
    >>> my_string
    'I hate pizza'
    >>> my_string = "I love %s but not %s" % ("Python", var)
    >>> my_string
    'I love Python but not pizza'

### Examples of integers and floats

```python
print("%i + %i = %i" % (1, 2, 3))
print("i = %f" % (9))
print("j = %.4f" % (3.14159))
print("k = %2i" % (5))
print("l = %2i" % (15))
print("m = %-2i" % (5))
print("o = %-2i" % (15))
```
Here's the output 

    1 + 2 = 3
    i = 9.000000
    j = 3.1416
    k =  5
    l = 15
    m = 5 
    o = 15

## Templates and the New String Formatting Methodology

    >>> print("I have an %(object)s" % {"object":"apple"})
    I have an apple
    >>> print("I have %(num)i apples" % {"num": 5})
    I have 5 apples
    >>> print("{0}, {2}, {1}".format("a", "b", "c"))
    a, c, b

    >>> xy = {"x": 3, "y": 9}
    >>> print("Graph a point at x={x}, y={y}.".format(**xy))
    Graph a point at x=3, y=9.

