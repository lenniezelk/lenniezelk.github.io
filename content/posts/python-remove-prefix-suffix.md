---
title: Python's removesuffix and removeprefix
date: 2021-02-27T14:11:52+03:00
tags:
  - programming
  - python
---

Python 3.9 added the string methods `removesuffix` and `removeprefix`. When I first saw this I wondered why, since the go-to solution for this is `strip`, `lstrip` and `rstrip`.

On diving into the documentation, I was surprised to find that `strip`, `lstrip` and `rstrip` treat the input chars as a set of characters to remove not a substring. An example will better explain this. Take for example you have the string `test_some_stuff` and you want to remove the prefix. The obvious way would be to go for `lstrip`.

```
s = 'test_some_stuff'.lstrip('test_')
```

The expected output is `some_stuff`. The actual output is `ome_stuff`. You see the \*strip methods will check the string for any of the set of characters provided and remove those from the string until a non-matching character. In the example above the `s` is `some` was also removed.
The solution is to use `removeprefix` and/or `removesuffix`.

```
s = 'test_some_stuff'.removeprefix('test_')
```

Output: `some_stuff`
If you desire to dig into this more have a look at the PEP that led to these two methods getting added.
https://www.python.org/dev/peps/pep-0616/
