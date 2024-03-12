+++
title = "Troubleshooting Windows Crashes"
+++
> :umbrella: MyPaint can often keep running if you get an exception.  
> :boom: This page is about the other kind of fault.  
> :mag: _Keywords:_ APPCRASH, segfault, backtrace, debugging, Windows, "python2w.exe has stopped working".

## Crashes on Windows

This page explains how you can get good low-level debugging information on Windows with MSYS2. Its goal is to get you confident enough to make a detailed forensic backtrace using the GNU debugger, _gdb_.

There are two types of crash MyPaint can encounter: high-level Python ones which you may be able to recover from, and low-level C/C++ API crashes which you definitely can't recover from because the Python interpreter just breaks suddenly. This page is about the low-level type of crash, the type that rudely kills MyPaint and loses your work. :boom:

> ![A Windows APPCRASH dialog](https://cloud.githubusercontent.com/assets/61299/15358983/0a229e2c-1cff-11e6-9d52-afc5b4691f17.png)  
> You can get a little more information by clicking on “View problem details”, but not much.

You may see a “[Program] has stopped working” dialog like the one above when this happens. The dialog only appears when you run MyPaint by clicking on an icon, or when you launch it using the Start menu.

## What you need

* You'll need to install MSYS2 first. See our [[Installing MSYS2 on Windows]] guide for notes.
* You'll also need a little familiarity with using a computer's command line (not much).
* Don't worry, we'll guide you through most of the debugging process :footprints: 

## Getting started

If you're here because MyPaint crashed, you will also need to figure out how to do a standalone build of MyPaint which you can run in-place. See [README_WINDOWS.md](https://github.com/mypaint/mypaint/blob/master/README_WINDOWS.md). You will need to be able to comfortable with rebuilding MyPaint from git.

The next step is to make sure you can reproduce the bug. Find out to your own satisfaction how to reproduce the crash, and make sure you can do it over and over again. You'll be doing that quite a lot in the next steps. :white_check_mark: 

## First investigations :mag:

The first thing to do is to investigate the problem without touching anything. When you click on View program details in the dialog above, Windows will reveal some diagnostic information which looks a little like:

```
Problem signature:
Problem Event Name: APPCRASH
Application Name: python2.exe
Application Version: 0.0.0.0
Application Timestamp: 30024206
Fault Module Name: libgdk-3-0.dll
Fault Module Version: 3.20.3.0
Fault Module Timestamp: 00000000
Exception Code: c000041d
Exception Offset: 0000000000033cca
OS Version: 6.1.7601.2.1.0.256.48
Locale ID: 1033
Additional Information 1: 5eea
Additional Information 2: 5eea6f5d39cc08d9e4b0c0a306963235
Additional Information 3: 7754
Additional Information 4: 7754a6285473c0e7ca3675dd2e053c0b
```

This identifies the module in which the crash occurred (GDK), and the version of that module (3.20.3). The rest of the details are not very relevant for our kind of debugging.

You don't always see the dialog though. If you are doing an in-tree test of MyPaint on the :computer:**MSYS64** command line and getting the same crash, you won't get the dialog. This is when you need to start using _gdb_ for the first time.

### Running GDB

You will need to use the native Windows/PE shell in MSYS2 :computer:**MSYS64**. First, make sure _gdb_ is installed:

```sh
$ pacman -S mingw-w64-x86_64-gdb
$ gdb --version
GNU gdb (GDB) 7.11
```

Then you can launch a :beetle:**gdb** session with MyPaint, or any other program that's crashing. It's simplest to make gdb run MyPaint immediately:

```gdb
$ gdb -ex r --args python ./mypaint -c /tmp/debug-cfg-1
[...]
Thread 1 received signal SIGSEGV, Segmentation fault.
0x0000000070ef3e1a in ?? () from C:\msys64\mingw64\bin\libgdk-3-0.dll
(gdb) 
```

The lines above mean that :beetle:**gdb** stopped at the crash, and is waiting for commands. The most useful command is `bt` (backtrace). This spits out a trace of which functions were calling which other functions within the program. However its information is only good for debugging if you have the names of the functions available. You need to have debugging symbols built into the libraries that are being used in order to see the function names.

Here's an example of a partial backtrace. Note how sometimes we know which function was being called and from which library ([DLL file](https://en.wikipedia.org/wiki/Dynamic-link_library)). For others, we only know the library DLL, and the situation is hazy otherwise :8ball: 

```gdb
$ gdb -ex r --args gtk3-demo
(gdb) bt
#0  0x0000000070eea1f6 in ?? () from C:\msys64\mingw64\bin\libgdk-3-0.dll
#1  0x0000000063a4ae78 in g_object_new_internal (class=0x1f52b20,
    class@entry=0x6864a9c0 <private_thread_memory>,
    params=params@entry=0x22f450, n_params=n_params@entry=1)
    at ../../glib-2.48.0/gobject/gobject.c:1821
#2  0x0000000063a4c90d in g_object_new_valist (
    object_type=object_type@entry=32841984,
    first_property_name=first_property_name@entry=0x70f3c1dc "display",
    var_args=<optimized out>, var_args@entry=0x22f600 "")
    at ../../glib-2.48.0/gobject/gobject.c:2040
#3  0x0000000063a4ca04 in g_object_new (object_type=32841984,
    first_property_name=0x70f3c1dc "display")
    at ../../glib-2.48.0/gobject/gobject.c:1624
#4  0x0000000070eede85 in ?? () from C:\msys64\mingw64\bin\libgdk-3-0.dll
#5  0x0000000070eca6da in ?? () from C:\msys64\mingw64\bin\libgdk-3-0.dll
[...]
#20 0x000000000040152b in ?? ()
#21 0x0000000076d659ed in KERNEL32!BaseThreadInitThunk ()
   from C:\Windows\system32\kernel32.dll
#22 0x0000000076e9b371 in ntdll!RtlUserThreadStart ()
   from C:\Windows\SYSTEM32\ntdll.dll
#23 0x0000000000000000 in ?? ()
Backtrace stopped: previous frame inner to this frame (corrupt stack?)
```

Stack frame `#0` is where the crash happened. There is a continuous chain of calls from the outmost frame `#23` all the way to it, starting from the Windows system's `ntdll` starting a new user thread for the program.

The `?? ()` lines are where _gdb_ doesn't know what function was being called at that point. This is common for all normal MSYS2 packages, so you often need to make a debugging build of GTK to find out more. 

NOTE: if you're pasting the backtrace above into a Github issue, please take time to [wrap it in ``` markers](https://help.github.com/articles/creating-and-highlighting-code-blocks/). If you don't, the `#1` through `#23` markers will be linked to other issue reports.

#### Common problem libs

It's worth knowing what the components that cause low-level crashes in MyPaint are. The most common libraries we see in bug reports and backtraces are:

* [GTK+](https://en.wikipedia.org/wiki/GTK%2B) :free::unlock:
  - This is a large group of functions for creating on-screen dialogs and controls.
  - It's _Free (Libre) Open-Source Software_, so you can rebuild it with debug information if you need.
  - GTK+ function names all start with `gtk_`, and its library is named `libgtk-3-0.dll`.
* [GDK](https://en.wikipedia.org/wiki/GDK) :free::unlock:
  - This is part of GTK. Many bugs relating to tablet input on Windows are caused by regressions in the GDK sub-component.
  - It handles input events (position updates with pressure), and its job is to translate lower-level events into higher-level events that code written against GTK and GDK can use.
  - GDK function names all start with `gdk_`, and its library is named `libgdk-3-0.dll`.
* [GLib](https://en.wikipedia.org/wiki/GLib) :free::unlock:
  - This is a lower-level library that contains utility code for other libraries.
  - It's Free/Open-Source Software, so you can rebuild it with debug information if you need.
  - Often you won't need to rebuild this for debugging things happening in GTK or GDK.
* [Wintab](http://www.wacomeng.com/windows/docs/WintabBackground.htm) :closed_lock_with_key:
  - This is a Windows-specific glue layer between your tablet's drivers and GDK.
  - A Wintab implementation will be provided by your tablet manufacturer as part of its driver installation bundle.
  - It's typically closed source, so normal users cannot recompile it. Nevertheless, sometimes it contains debug information that _gdb_ can use.
  - Wintab function names normally start with `WT`, and its library is named `wintab32.dll`.
  - You normally cannot report bugs publicly online, except as directed by the private company who made your tablet and its drivers.

Remember, the MyPaint Development Team doesn't control these components and their projects. The only thing we or you can do to help fix a bug there is to report the problem. Providing a good _gdb_ backtrace is an important part of this process. A good backtrace helps the upstream module's developers understand the bug enough to fix it.

And you can only make good backtraces if you have libs which are built with debugging information.

### Making a debug build of GTK+ :hourglass:

Taking it any further requires a debugging build of the problem module, and nearby modules to it that you saw in the initial _gdb_ backtrace. We're also going to make a more thorough type of backtrace this time.

* See [[Building GTK3 from git on Windows]].

#### TBD: example debugging session



#### Going back to normal

All of the above changes can be undone quite easily. You can get back to the current MSYS2 package for gtk3 like this, from either an :computer:**MSYS2** or a :computer:**MINGW64** shell:

```
$ pacman -S mingw-w64-x86_64-gtk3
```

### Other lines of inquiry

Here are some other things to try:

* Does the problem you are seeing happen with `gtk3-demo` when you run it from the command line?

### See also

* [[Fixing Bugs#diagnosing]]
* MyPaint's [DEBUGGING.md](https://github.com/mypaint/mypaint/blob/master/DEBUGGING.md) for a summary of this from a Linux/Unix perspective.
* GNU's [GDB Documentation](https://www.gnu.org/software/gdb/documentation/).
* MSYS2's [docs for makepkg-mingw](https://sourceforge.net/p/msys2/wiki/Contributing%20to%20MSYS2/).
