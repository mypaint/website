+++
title = "My icons are missing!"
summary = "MyPaint won't start: \"can't run sensibly without its icons\""
+++

MyPaint won't start: "can't run sensibly without its icons"

Symptoms: MyPaint refuses to start, and you get a message like the following in the output.

```
ERROR: gui.application: Missing icon 'mypaint-brush-symbolic': check that librsvg is installed, and update loaders.cache
Traceback (most recent call last):
  File "/usr/share/mypaint/gui/application.py", line 126, in _init_icons
    pixbuf = icon_theme.load_icon(icon_name, 32, 0)
[...]
CRITICAL: gui.application: Required icon(s) missing
ERROR: gui.application: Icon search path: [...]
ERROR: gui.application: MyPaint can't run sensibly without its icons; please check your installation. See https://github.com/mypaint/mypaint/wiki/FAQ-Missing-icons for possible solutions.
```

# Why this is happening

This is a fairly common user-reported fault, so common in fact that we had to write a special check for it in the startup code. It's caused by MyPaint not being able to load its icons. If they're absent, your toolbar will be very blank, and you won't be able to get much done!

The underlying cause is normally a broken installation, where one of the following conditions isn't true:

* Your `librsvg` (SVG rendering library) must:
  - Actually be installed.
  - Have been built against `gdk-pixbuf`.
  - Provide a loader for SVG graphics named `libpixbufloader-svg.so`.
  - Have that loader listed in `loaders.cache` so that `gdk-pixbuf` can find it.
* Your `gdk-pixbuf` (bitmap graphics library) must be able to link with `libpixbufloader-svg.so` when it needs to.
  - Dependencies of `librsvg` can sometimes cause issues here: see [#780](/mypaint/mypaint/issues/780).
* Your icon cache for the `hicolor` icon theme must be up to date, if you have one.

This shouldn't happen if you run MyPaint from a decently managed stable distribution of Linux, or a monolithic installation like our Windows bundles. However, some Linux distros are quite bleeding-edge, and things sometimes do go wrong.

# Fixing it

## The SVG loader library

MyPaint's icons and vector layers are SVG files, and they must be loaded into in-memory bitmaps to be used. Therefore, MyPaint uses the standard library in its ecosystem to do this, `gdk-pixbuf`. Gdk-pixbuf, in turn, uses another library called `librsvg` to do the SVG rendering, and it loads it in through a plugin.

Let's assume that you've installed MyPaint's `librsvg` dependency properly. Its standard configuration should just work, MyPaint doesn't make you recompile your world for the sake of art. The usual bit that goes wrong is the cache file, `loaders.cache`. Regenerate this with

    sudo gdk-pixbuf-query-loaders --update-cache

This updates the _default_ gdk-pixbuf cache, which on my system is `/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0/2.10.0/loaders.cache`. The path will probably be different on your system! If you have a look at that file, it should now mention `libpixbufloader-svg.so`, which is installed near the `loaders.cache` file.

## Runtime linker issues

When you try to update the cache, you may get a message about `g_module_open()` encountering an `undefined symbol` when it tries to pull in `libpixbufloader-svg.so`. This is a runtime linking issue: it's looking for a function that isn't there.

Situations like this can only be solved by recompiling the library in question, or obtaining a properly linked version of the library or libraries from your distribution's package repository. You should check your distro's bug tracker to see if it has been reported there, and follow up appropriately.

## Icon caches

Take care to update the icon theme cache for your prefix if you're installing MyPaint to a location which has one of these files already. If you install new icons, any existing icon cache must be updated too, otherwise MyPaint won't be able to find its icons even if it looks in the right place.

For example for an install into `/usr`, which has an icon cache on most systems, you should run:

    sudo gtk-update-icon-cache /usr/share/icons/hicolor
    sudo chmod a+r /usr/share/icons/hicolor/icon-theme.cache

after installation to ensure that the cache is up to date. Our build system won't do this for you because the cache file is optional, and build systems shouldn't manage your prefix for you anyway - that's a package manager's job.

If you install to `/usr/local`, you may need to run this instead:

    sudo gtk-update-icon-cache --ignore-theme-index /usr/local/share/icons/hicolor

As before, make sure that it's globally readable.
