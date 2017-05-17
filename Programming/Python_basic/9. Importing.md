* noted by Erebuszz, modified on 5/17/2017

* Excerpts from << Python 101 >>

An "Easter Egg" in Python
```python
import this
```
Output

    The Zen of Python, by Tim Peters

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!

```python
import math
print(math.sqrt(4))
```
Output

    2.0

> syntax: <b>module_name.method_name(argument)</b>

# Using from to import

```python
from math import sqrt
print(sqrt(16))
```

import multiple methods

```python
from math import pi, sqrt
```

# Import Everything!

```python
from math import *
```

This is actually a <b>bad</b> idea as it can contaminate your namespace

There is a few exceptions to this rule. One prominent example is <b>Tkinter</b>, a toolkit that allows you to create desktop user interfaces. The reason is that the modules are named so that it is unlikely you would reuse one yourself