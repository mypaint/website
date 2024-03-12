+++
title = "Troubleshooting Windows Tablets"
summary = "Tablet glitches are harder to deal with on Windows.  Here's how to help get them fixed."
+++

We get a lot of reported tablet issues on Windows which are a result of us using a separate library called [GDK][gdk] to handle tablet input. The "win32" backend to GDK is not very thoroughly tested for all possible tablets, because Windows is a minority operating system for the parent [GTK+][gtk] project. Tablet support can be particularly hard to get working because the GTK developers don't have access to all tablet models out there.

When it works, it works. You may have to trust me on that. When it doesn't work, you may see:

* _Loss of precision:_ i.e. offsets between the cursor and the paint position. May be caused by multiple monitors.
* _Crashes:_ These are upstream issues which need to be reported to [GTK]'s bug tracker. See [[Debugging crashes on Windows]] for a quick intro to capturing the info the developers will need.
* _Missing pressure or tilt._ This may be caused by an incomplete tablet setup, or by a missing `wintab32.dll`.

We'll try to get you testing so that you can report the problem appropriately. But don't be discouraged if we ask you to report the problem elsewhere if it proves to be not our fault.

### Testing with `gtk3-demo` from MyPaint

With the [latest version](https://github.com/mypaint/mypaint/releases/tag/v1.2.1), MyPaint comes with a tool called `gtk3-demo`. You can use this tool to help you decide whether the problem is within MyPaint or within GDK.

For example, if you do not get pen pressure in MyPaint, please test in gtk3-demo as well.

* If that also does not have pen pressure, then your bug is not in MyPaint. It needs to be reported upstream, to the GTK+ developers.
* If GTK3-Demo shows pressure, but MyPaint doesn't, then this is a MyPaint issue: no need to bug the upstream developers about it.

To open up the `gtk3-demo`, go to Start > MyPaint > "Test MyPaint-w64's tablet support (GTK3-Demo)". It will be called  "Test MyPaint-w32's Tablet Support (GTK3-Demo)" instead, for w32 installs.

### Testing with latest `gtk3-demo` from MSYS2
 
Sometimes tablet problem are already fixed on GDK but aren't present in any MyPaint bundles. To test against the latest GDK library, you will have to use [MSYS2](https://msys2.github.io/)'s `gtk3-demo` program. These instructions assume you are using a 64-bit Windows PC, windows 7 or later: 

1. Install `msys2-x86_64-20161025.exe` or later from <https://msys2.github.io/> in the time-honoured Windows way.

2. In an MSYS2 shell, at the $ prompt, type:

  ```
  pacman -Syyuu ⏎
  ```

  Then follow the instructions in the output to update MSYS2.
  The ⏎ means to press the _Return_ or _Enter_ key - the one used to end paragraphs.
  It may have a symbol like ⏎ instead.

  MSYS2 is a rolling software distribution,
  so you need to catch up before moving on to the next bit.

3. Next, launch another MSYS2 shell, and type:

  ```
  mkdir -p /mingw{32,64} ⏎
  pacman -S msys2-launcher-git ⏎
  pacman -S mingw-w64-x86_64-gtk3 ⏎
  ```

  This installs the demo program we'd like you to use.

4. Start a "native" MINGW64 shell using `mingw64.exe` or one of the shortcuts. In it, type:

  ```
  gtk3-demo --gdk-debug=input --run=event_axes ⏎
  ```

  This is a graphical test, and you can make the tablet test window bigger.

  ![image](https://cloud.githubusercontent.com/assets/61299/18417086/9491ec50-781e-11e6-884a-eec501a34aaa.png)

  However the terminal output that gets shown as a result of the `--gdk-debug=input` parameter
  is very relevant for bug reporting as well.
  Please help us by pasting it into your bug report.

## Reporting bugs in GTK or GDK

Bugs in these upstream libraries are handled via the GNOME project's bugzilla:

* [Search](https://bugzilla.gnome.org/query.cgi) for your bug first. Likely keywords are:
  - “[wintab](https://bugzilla.gnome.org/buglist.cgi?bug_status=__all__&content=wintab&list_id=191697&order=bug_id%20DESC&product=gtk%2B&query_format=specific)”
  - Your graphics tablet's model name, or it's exact model number.
* [Report](https://bugzilla.gnome.org/enter_bug.cgi?product=gtk%2B) a bug against the "Backend: Win32" component if you don't see your problem listed. This requires a login.
* [Example of a really good upstream bug report.](https://bugzilla.gnome.org/show_bug.cgi?id=778328)
* If there's a related MyPaint issue, even a closed one, it's helpful to link to the upstream report in a comment so that other people can find it.

The GTK developers will need to know the exact version of libgtk that you're using. If it's a recent MyPaint release, you can find this technical information in the about box, 

## Reporting bugs in MyPaint

* Search our [Github issue tracker](https://github.com/mypaint/mypaint/issues) before reporting. 
  - Example search: “[wintab](https://github.com/mypaint/mypaint/issues?utf8=%E2%9C%93&q=is%3Aissue%20wintab%20)”.
* You can report a new bug with the green “New issue” button.
* See [[Reporting Bugs]] for step-by-step information about making a good bug report.

[gtk]: https://www.gtk.org/
[gdk]: https://git.gnome.org/browse/gtk+/tree/gdk/
