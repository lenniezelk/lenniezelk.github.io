<!--
.. title: Improving readability of Python code
.. slug: type-hints-in-python
.. date: 2018-11-24 14:11:52 UTC+03:00
.. tags: python, programmming 
.. category: python 
.. link: 
.. description: 
.. type: text
-->

Readability of code as defined in wikipedia:
```
In computer programming, readability refers to the ease with which a human reader can comprehend the purpose,
control flow, and operation of source code
```
Python is one of the most readable programming languages out there but we can still improve this more by following software
development best practises and tools provided by Python core language and the Python community. By software development best practises
I am referring to writing clean code. Watch things like:

* Use good descriptive variable and function names
* Follow SOLID priciples
* Keep functions short
* Follow coding conventions for your programming language e.g PEP8

For Python, type hinting is also a good option since version 3.5. This will be my main focus for this article.

In this article I am only going to refer to tools specific to Python, later I will add another article on SOLID with examples in Python.
Python uses duck typing to determine the type of a variable. This usually leads to criticism where people say it reduces
readability and I agree with them. I have been using Python for the past five years and its annoying having to read a
function body in order know the type of parameters passed in. If its a dictionary passed in or tuple its worse because you
have to look through the code to know the type of keys and values of the `dict`. I've had to add print statements to determine
the type being passed in.

```
#!python
def check_status(project, date):
    pass
```

In the code above `project` and  `date` could be anything. Proper naming of the variables helps but still, `project` could
be an `int`, the project database id or a user defined class instance. `date` could be an `int` or `datetime.date` object.
This is the problem typing module was added to solve. I don't think types within the function body are a huge deal since
you can usually determine this from the context, even in Kotlin you don't have to specify the type when declaring a variable
it can usually be infered from the context.

With Python's type hints you can specify the parameter being passed to a function.

```
#!python
from datetime import date

from .projects import Project

def check_status(project: Project, date: date):
    pass
```

I'm a huge fan of namedtuples, they have a smaller memory footprint compared to classes and are more descriptive that tuples. Typing
takes their descriptiveness to a new level. You can specify the type for the field names.

```
from typing import NamedTuple

class Truck(NamedTuple):
    num_wheels: int
    num_axles: int
```
