+++
title = "Why won't MyPaint Start on Mac?"
tags = ["X11"]
+++

# The problem
I just installed MyPaint via ``sudo port install mypaint``, but it won't start!

The last line MyPaint says when run in the terminal is:

```shell
AttributeError: 'NoneType' object has no attribute 'append_search_path'
```

# The Answer
From [this comment][comment] on GitHub:

In a default MacPorts installation, MyPaint uses [X11][X11]. Therefore you must install
an [X11 server][X11-MacPorts]. MacPorts doesn't do it automatically because it doesn't know which
one you want.

## Steps to Take
1. Run `sudo port install xorg-server` in the command line.
2. Log out and log back in.

[comment]: https://github.com/mypaint/mypaint/issues/1154#issuecomment-1264564317
[X11]: https://en.wikipedia.org/wiki/X11
[X11-MacPorts]: https://ports.macports.org/port/xorg-server/
