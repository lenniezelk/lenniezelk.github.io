<!--
.. title: Named Parameters in Dart, Swift and Python
.. slug: named-parameters-in-dart-swift-and-python
.. date: 2020-03-23 12:20:58 UTC+03:00
.. tags: python, swift, dart
.. category: programming
.. link: 
.. description: 
.. type: text
-->

In software development we optimize for readability since code is read more than its written. Named parameters are one way to improve code readability. Lets say we have a function that calculates the distance between two points. I takes two point `Point` class instances representing the start and end positions. When calling the functions, using positional arguments its not very clear what is being referred to.

In Python:

..gist::d80e6e2bbf9ab513654aa97e43f37fc6

In Dart:

..gist::9edb982793fda8440be6d22219f96129


In Swift:

..gist::100a5abd8670331750435a8b0ff719de


On the other hand, using named parameters makes function calls more expressive, its clear to the reader what the arguments represent. This becomes helpful particularly as the number of arguments grow. Lets add one more argument. In the examples below when calling the functions its not very clear what the third argument is when its being read.

..gist::fa6f6cd79647c97c2997160a0998d028

..gist::18d19b34c43454518b3195f704d0576f

..gist::694317b02b1abb74cd322fadb8f795a0

Using named parameters is really helpful in such a situation. In the three languages its possible to specify that the parameters should be passed as named parameters. In Python, we can add a `*,` before the parameters, in dart we can add curly braces around the parameters and in swift we can remove the underscore before the parameter names.


..gist::1ca8b8c2615e45b779d074c4a57bd7c7

..gist::dfe21e1755ca663ec82b2ea8bf017778

..gist::19c64a6b97bc7c6be70cf8d9f6e508d6
