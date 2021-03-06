* noted by Erebuszz, modified on 5/17/2017

* Excerpts from << Python 101 >>

Create a text file named test.txt

    This is a test file
    line 2 
    line 3
    (This is a blank line)

```python
# open test.txt in read-only mode (default)
# look in the folder the script is running
handle = open("test.txt")
```

# Raw string vs. normal string

On Windows, the path use backslashes, which may accidentally make special characters, e.g.

    >>> print("C:\Users\mike\py101book\data\test.txt")
    C:\Users\mike\py101book\data    est.txt
    >>> print(r"C:\Users\mike\py101book\data\test.txt")
    C:\Users\mike\py101book\data\test.txt

# How to read a file

```python
# open the file in a full qualified path 
# treat the path as a raw string (first r)
# open as read-only mode (second "r")
handle = open(r"/Users/erebus/Github/demo_project/test.txt", "r")
# read the entire file
data = handle.read()
print(data)
# close the file to help save the memory and prevent bugs
handle.close()
```
Output

    This is a test file
    line 2 
    line 3
    (blank line)

# readline(), readlines()

```python
handle = open("test.txt", "r")
data = handle.readline()    # read just one line
print(data)
handle.close()
```
Output

    This is a test file    

```python
handle = open("test.txt", "r")
data = handle.readlines()    # read all the lines and make it a list
print(data)
handle.close()
```
Output

    ['This is a test file\n', 'line 2 \n', 'line 3\n']

# Read files piece by piece

```python
handle = open("test.txt", "r")
for line in handle:
    print(line)
handle.close()
```
Output

    This is a test file
    (blank line)
    line 2 
    (blank line)
    line 3
    (blank line)
    (blank line)

> print will change the line automatically, and the lines comtain \n themselves, so there will be extra blank lines

```python
handle = open("test.txt", "r")

while True:
    data = handle.read(1024)    # read a kilobyte of the file
    print(data)
    if not data:
        break
```

# Read a Binary file

```python
handle = open("test.pdf", "rb")
```

# How to write a file

### *<b>CAUTION:</b>* When using "w" or "wb" modes, if the file already exists, it will be overwritten with no warning! You can go to <b>os.path.exists</b> to see how to check if a file exists

```python
handle = open("test.txt", "w")
handle.write("This is a test!")
handle.close()
```

The file handle also has a <b>writelines</b> method that will accept a list of strings that the handle will then write to desk in order

* Use "a" instead of "w" to append stuff from the end of the file
* Use "w+"or "a+" to read and write at the same time

# Using the <b>with</b> operator

Used to simplify reading and writing files, the operator will automatically close the file for you when you are done processing it

```python
with open("test.txt") as file_handler:
    for line in file_handler:
        print(line)
```