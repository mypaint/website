+++
title = "Programming Style Guide"
+++

Code committed into the MyPaint project repos follows consistent style rules to
improve readability for other contributors. In general, please follow the coding
conventions of the files you are editing. New Python code should follow this style
guide<!--more-->>

# Summary Of Rules
- [Document your code]({{< relref "documentation#python" >}})
- All contributed program code should be wrapped at 78 columns regardless of language.
- Python docstrings should be wrapped at 72 columns.
- Use four spaces per indent level for Python, C, C++, and shell
- Use two spaces per level for XML code.
- Don't use [visual indendation]({{< relref "#visual-indentation" >}})
- Use [``str.format``]({{< relref "#strings" >}})
- Write [localisable python](
{{< relref "/docs/contributing/translating/maintaining-translations#writing-localisable-python" >}})

# Python Rules
- [PEP 8](http://www.python.org/dev/peps/pep-0008/) applies, with a few exceptions, documented in [setup.cfg](https://github.com/mypaint/mypaint/blob/master/setup.cfg). Please use [flake8](https://gitlab.com/pycqa/flake8) to check over your changes before sending a PR.
- Please try to follow the [Google Python Style Guide](http://google-styleguide.googlecode.com/svn/trunk/pyguide.html). It's well thought out and thorough, while not being onerous.
* Make your code pretty and readable! Brandon Rhodes's [A Python Æsthetic](http://rhodesmill.org/brandon/slides/2012-11-pyconca/) is a great place to start.
- [Don't commit dead code]({{< relref "git#dead-code" >}})

## Guides
- Constantine Lignos's [Anti-Patterns in Python Programming](http://lignos.org/py_antipatterns/) covers some common coding pitfalls.

# Specific Rules
## Visual Indentation
Visual indentation makes it hard to maintain things, and also ends up making things
really cramped.

```python
# (don't do this)
x = run_function_with_really_long_name(argument1,
```

For functions that take a *lot* of arguments, prefer:

```python
# (this is better)
x = wow_this_sure_is_a_pretty_complicated_function(
    arg1, arg2,
    really_long_argument,
    named_arg = "something",
)
```

This is also recommended for long array/tuple/etc literals:

```python
x = [
    "something",
    "another thing",
    "etc",
]
```

## Strings
We now prefer [`str.format`][python-str.format] (and `unicode.format`) over C-style
`"%s"` interpolation. It's much easier to read, and far friendlier to our translators.

The exception to this rule is for hard-coded status messages sent to the program's
log output(s). The standard `logging` module requires C-style formatting, so please
use `%r` there for interpolated objects.

[python-str.format]: https://docs.python.org/3/library/stdtypes.html?highlight=str.format#str.format
