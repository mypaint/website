+++
title = "GUI"
+++

MyPaint uses [GObject-Introspection](https://wiki.gnome.org/Projects/GObjectIntrospection)
(“GI”) to access certain third-party libraries. This is a mechanism that allows
library code written in a compiled language to be used by scripting languages. It's
normally not possible to do this directly. The Python library for using other libs
through GI is called [PyGObject](https://wiki.gnome.org/Projects/PyGObject) or PyGI.<!--more-->

# Discovering PyGI
It's easy to spot Python code which uses it: it will always have imports looking
like the following near the top.

```python
from gi.repository import Gdk
from gi.repository import Gtk
```

GObject-Introspection rewrites the names of class definitions, methods, and functions
so that they make the most sense in the target language. For example, if you're
constructing a GTK button in C, you'd do

```C
GtkWidget *button = gtk_button_new(...);
gtk_button_set_label(button, "Click me");
```

but the equivalent Python code is

```python
button = Gtk.Button()
button.set_label("Click me")
```

The documentation for GTK and GDK is not readily available through GI. You have
to consult the C API documentation for the library instead. To make matching up
the C function/class names and their Python equivalents, you can use [pygi-grep][pygi-grep],
a tool for searching Python-GObject namespaces.

[pygi-grep]:(https://gist.github.com/achadwick/2647305f34fb31169f2)

    $ pygi-grep -vi -r 3.0 Gtk tree.*row
    from gi.repository import Gtk
    Gtk.TreeModelRow
    Gtk.TreeModelRowIter
    Gtk.TreeRowReference
    Gtk.tree_get_row_drag_data
    Gtk.tree_row_reference_deleted
    Gtk.tree_row_reference_inserted
    Gtk.tree_set_row_drag_data

# Learning GTK+ and GDK
The C interfaces for GTK+ and GDK are well documented:

* [The Python GTK+ 3 Tutorial](http://python-gtk-3-tutorial.readthedocs.io/en/latest/index.html)
maintained by [Sebastian Pölsterl](https://github.com/sebp).
* [GNOME Developers: API references](https://developer.gnome.org/references)
  - [GTK+](https://developer.gnome.org/gtk3/stable/) - widgets and windows
  - [GDK](https://developer.gnome.org/gdk3/stable/) - input event and screen area abstractions
  - [GLib](https://developer.gnome.org/glib/stable/) - low-level abstractions and portability

You may also wish to install [Devhelp](https://wiki.gnome.org/Apps/Devhelp) for offline browsing.
