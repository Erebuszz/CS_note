* noted by Erebuszz, modified on 5/13/2017

* Excerpts from << Python 101 >>

# The <b>if</b> statement

    >>> if 10 > -10:
    ...     print("The condition is TRUE!")
    ...
    The condition is TRUE!

> Do <b>not</b> mix tabs and spaces together to indent the code

> You can actually indent your code any number of spaces as long as you are consistent. However, the <b>4-space</b> rule is one that is recommended by the Python Style Guide

```python
value = input("How much is the phone? ")
value = int(value)  # transfer the string to the integer

if(value < 10):
    print("That's cheap enough!")
elif(10 <= value <= 20):
    print("That's acceptable!")
else:
    print("That's a little expensive!")
```
Output
    
    How much is the phone? 15
    That's acceptable!

> In Python2.x, use <b>raw_input</b> instead

# Boolean Operations

* <b>or</b> means either of the conditions is true, then the result is true
* <b>and</b> means all of the conditions must be true, else the result is false
* <b>not</b> means to reverse the result from true to false, or false to true

```python
x = 15
y = 40

if(x == 15 and y < 40):
    print("Both of the conditions are right!")
elif(x == 15 or y < 40):
    print("Either / Both of the conditions is / are right!")
else:
    print("Both conditions are false!")
```
Output

    Either / Both of the conditions is / are right!

```python
my_list = [1, 2, 3, 4]
x = 10

if x not in my_list:
    print("10 is not in the list")
```
Output
    
    10 is not in the list

Another way to test for not
```python
x = 10

if x != 11:
    print("x is not equal to 11!")
```
Output

    x is not equal to 11!

# Checking for Nothing

```python
empty_tuple = ()
empty_string = ""

if empty_tuple:
    print("This is not an empty tuple")
if not empty_string:
    print("This is an empty string")
```
Output

    This is an empty string

Based on the output, we can see the if the variable is empty, the <b>if</b> statement will judge it as a <b>false</b> condition

> Note that none of these variables equals the other

    >>> empty_string == empty_list
    False

# Special Characters

```python
print("I want \na new line!")    # \n for a new line
print("The sentence is \ttabbed!")  # \t for tab
print("This is a backslash \\")
```
Output

    I want 
    a new line!
    The sentence is 	tabbed!
    This is a backslash \

# if \__name__ == "\__main__"

This tells Python that you only want to run the following code if this program is executed as a <b>standalone</b> file, see more in the chapter 11 about <b>classes</b>