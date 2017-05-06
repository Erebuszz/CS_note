# Python Notes

* noted by Erebuszz, modified on 5/6/2017

## Basic Operation

### <font color="lightblue">- Print</font>

In Python 2, <b>print</b> is a statement

    print "Hello from Python!"

In Python 3, print was turned into a print function

    print("Hello from Python!")

### <font color="lightblue">- Comments</font>

    # one line comment

    """ Multiline examples
    like this
    and this
    """

## Strings

### <font color="lightblue">- Create a string</font>

You can use single , double or triple quotes one of three ways

    my_string = "Welcome to Python!"
    another_string = 'Bla Bla Bla'
    a_long_string = '''This is a 
    multi-line string. It covers more than 
    one line.'''

The triple quoted line can be done with 
three single quotes or three double quotes

You will noticed that 
output retains the line breaks if you print it out

use the <b>str</b> methods
    
    my_number = 123
    my_string = str(my_number)

> Noted: string is one of Python <b>immutable</b> types

So, this will cause an error

    my_string = "abc"
    my_string[0] = "d"

Every time we assign a new value to the variable, 
its identity changes

    >>> string = "abc"
    >>> id(string)
    4302870376
    >>> string = "sdf"
    >>> id(string)
    4324422576

### <font color="lightblue">- String Concatenation</font>

    >>> string_one = "My dog ate "
    >>> string_two = "my homework."
    >>> string_three = string_one + string_two
    >>> string_three
    'My dog ate my homework.'

### <font color="lightblue">- String Methods</font>

> Everything in Python is an object

Strings have their own methods built into them, 
such as <b>upper()</b>

    >>> my_string = "abc"
    >>> my_string.upper()
    'ABC'

Type the following command in your interpreter 
to get a list of all the string methods:

    dir(my_string)

To learn what the methods is for, 
just ask for <b>help()</b><br>eg.

    >>> help(my_string.capitalize)
    Help on built-in function capitalize:

    capitalize(...) method of builtins.str instance
        S.capitalize() -> str

        Return a capitalized version of S, i.e. make the first character
        have upper case and the rest lower case.

Tell what type the variable is
    
    >>> type(my_string)
    <class 'str'>

### <font color="lightblue">- String Slicing</font>

