+++
title = "Unit Testing"
+++
We like to use `doctest` in Python code. There are a number of standalone test
scripts too. <!--more-->

```python
def tested_func(a, b):
    """Multiplies two things.

    >>> tested_func(42, 3)
    126
    >>> tested_func("A", 4)
    'AAAA'
    """
    # Feel free to write tests before you write any code.
```

The doctests in `lib/` and `brushlib/` are run by [Travis-CI](https://travis-ci.org/mypaint/mypaint)
whenever a new commit is made, because these are the tests which can run ‘headless’
(without a graphical user interface).

You can run the tests from the command line using the third-party `nose` tools.

```sh
$ sudo apt-get install python-nose
$ nosetests --with-doctest gui lib brushlib
```

Modules in `gui/` are difficult to write automated tests for, due to their GTK dependency.
Tests which rely on GTK objects may not run on a headless system, so they're omitted
from our Travis CI configuration. However, don't let that stop you from writing
tests for your GUI code. You can use doctest as above, or write your own test driver
for a module's widgets.
