* noted by Erebuszz, modified on 5/16/2017

* Excerpts from << Python 101 >>

# Common Exceptions

A list of the most common built-in exceptions <br>
(more in [Python Documentation!](https://docs.python.org/3.5/library/exceptions.html))

* <b>Exception</b> (this is almost all the others are built off of)
* <b>AttributeError</b> - Raised when an attribute reference or assignment fails
* <b>IOError</b> - Raised when an I/O operation (such as a print statement, the built-in open() function or a method of a file object) fails for an I/O-related reason, e.g., "file not found" or "disk full"
* <b>ImportError</b> - Raised when an import statement fails to find the module definition or when a <b>from ... import</b> fails to find a name that is to be imported
* <b>IndexError</b> - Raised when a sequence subscript is out of range
* <b>KeyError</b> - Raised when a mapping (dictionary) key is not found in the set of existing keys
* <b>KeyboardInterrupt</b> - Raised when the user hit the interrupt key (normally Ctrl-C or Delete)
* <b>NameError</b> - Raised when a local or global name is not found
* <b>OSError</b> - Raised when a function return a system-related error
* <b>SyntaxError</b> - Raised when the parser encounters a syntax error
* <b>TypeError</b> - Raised when an operation or function is applied to an object of inappropriate type. The associated value is a string giving details about the type mismatch
* <b>ValueError</b> - Raised when a built-in operation or function receives an argument that has the right type but an inappropriate value, and the situation is not described by a more precise exception such as IndexError
* <b>ZeroDivisionError</b> - Raised when the second argument of a division or modulo operation is zero

```python
try:
    1 / 0
except ZeroDivisionError:
    print("You can not devide by zero!")
```
Output

    You can not devide by zero!

```python
my_dict = {"a": 1, "b": 2, "c": 3}
try:
    value = my_dict["d"]
except KeyError:
    print("The key is does not exist!")

my_list = [1, 2, 3, 4, 5]
try:
    value = my_list[6]
except IndexError:
    print("The index is not in the list!")
```
Output

    The key is does not exist!
    The index is not in the list!

# Catch multiple excepts

```python
my_dict = {"a": 1, "b": 2, "c": 3}
try:
    value = my_dict["d"]
except (KeyError, IndexError):
    print("A KeyError or an IndexError occurred!")
```
Output

    A KeyError or an IndexError occurred!

# Don't know what the error gonna be

```python
try:
    fhandle = open("myfile", "w")
    fhandle.write("This is some data to dump into the file")
    print("Wrote some data to the file")
except IOError:
    print("Exception caught: Unable to write to myfile")
except Exception as e:
    print("Another error occured:", e)
else:
    print("File written successfully!")
    fhandle.close()
```

# The finally statement

```python
my_dict = {"a": 1, "b": 2, "c": 3}
try:
    value = my_dict["d"]
except KeyError:
    print("The key is does not exist!")
finally:
    print("I will always be executed")
```
Output

    The key is does not exist!
    I will always be executed

# The else statement

```python
my_dict = {"a": 1, "b": 2, "c": 3}
try:
    value = my_dict["d"]
except KeyError:
    print("The key is does not exist!")
else:
    print("Only run if there are no errors raised!")
```
Output

    The key is does not exist!

