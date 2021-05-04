---
title: Pattern Matching in Python
date: 2021-03-20T14:11:52+03:00
tags:
  - programming
  - python
---

Python 3.10 has introduced [Pattern Matching](https://en.wikipedia.org/wiki/Pattern_matching). I've been eager to try this out for some time now. I first found out about pattern matching when I tried out Elixir lang a while back. Python 3.10 is still pre-release, you can download it [here](https://www.python.org/downloads/release/python-3100a6/) or use [asdf](https://asdf-vm.com/#/) to install it.

Let's go through some use-cases which will help in gaining a good grasp of what's possible with pattern matching. In my day job, I use the Django web framework for developing web applications and create RESTful APIs. A common pattern when creating objects and saving in DB is:

{{< gist lenniezelk 60d3b9e545ce122da522a0c803450c64 >}}

`get_or_create` returns a tuple of the user and a bool indicating whether the user was created or was just fetched from DB.

A different approach using pattern matching would be:

{{< gist lenniezelk 941ccd8709a220729ee6715ba5ae8997 >}}

The first case matches when a new user is created, and the second matches when the user was not created.
Now, this takes away the readability a bit but `get_or_create` is common enough in Django to allow for this. In most cases weigh out the loss of readability vs the gains particularly in the beginning before pattern matching becomes common in the Python community.

Pattern matching allows for guards. Let's say you need to carry out some action if the newly created user is a superuser:

{{< gist lenniezelk 12a0c84cfc94bb03670b80b8e92fe03b >}}

The first case would match for newly created superusers and the second for the other newly created users.

Another use-case would be pattern matching the response code when fetching data from the internet using for example the requests library:

{{< gist lenniezelk e7e4c4427347aa5fdff1bdfd9b66e25b >}}

The `401 | 403` is combining several literals in a single pattern. In other words `401 or 403`.

It is possible to pattern match on dictionary key and values. For example, if you fetch some data and want to extract specific fields from the response dict:

{{< gist lenniezelk 9032ff0aacf00a59c7dd254d3019f118 >}}

The first case captures the values for `id` and `email` and ignores the rest.

I hope this whets your appetite for pattern matching in Python. To learn more on this have a look at Guido's [tutorial](https://github.com/gvanrossum/patma#tutorial).
