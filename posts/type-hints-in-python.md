<!--
.. title: Type hints in Python
.. slug: type-hints-in-python
.. date: 2018-11-24 14:11:52 UTC+03:00
.. tags: python, programmming 
.. category: python 
.. link: 
.. description: 
.. type: text
-->

Python uses duck typing to determine the type of a variable. This usually leads to criticism where people say it reduces
readability and I agree with them. I have been using Python for the past five years and its annoying having to read a
function body in order know the type of parameters passed in. If its a dictionary passed in or tuple its worse because you
have to look through the code to know the types being passed. I've had to add print statements to determine the type being
passed in.

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
