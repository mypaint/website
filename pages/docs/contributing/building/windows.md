+++
title = "Windows Build Environment"
+++

The MyPaint project builds for Windows using [MSYS2][MSYS2], a development environment
based off of [Cygwin][cygwin] with a focus on building Windows-native software.<!--more-->

[MSYS2]: https://www.msys2.org/
[cygwin]: https://www.cygwin.com/

1. Follow MSYS2's [getting started guide][MSYS2]. The MSYS2 environment will either
be installed at `c:\msys32` or `c:\msys64`.
2. Install important development dependencies
```bash
$ pacman --sync --needed --noconfirm base-devel mingw-w64-{i686,x86_64}-toolchain
```

# Building GTK3 From Source
GTK3 (the GUI toolkit used by MyPaint) is packaged in the MSYS shell, but you may
want to install it from source. Unless specified otherwise, {{< colour "yellow" >}}
run these commands in the MSYS shell.{{< /colour >}}
1. Download and unpack GTK3:
    - The following code block unpacks GTK3 into `src/gtk3`
(`C:\msys32\usr\src\MINGW-packages\mingw-w64-gtk3-git\src\gtk3` in the Windows filesystem).
```bash
$ cd /usr/src
$ git clone https://github.com/Alexpux/MINGW-packages.git
$ cd MINGW-packages/mingw-w64-gtk3-git
$ makepkg-mingw --syncdeps --nobuild   # unpack but don't build
```
2. Build GTK3:
    - `makepkg-mingw` normally builds for both `MINGW32` and `MINGW64`. The ``MINGW_INSTALLS``
variable species which target to build for.
```bash
$ MINGW_INSTALLS=mingw64  makepkg-mingw --force --holdver --noextract
```
3. Install GTK3:
    - The results of the final build command are `.pkg.tar.xz` files in the `mingw-w64-gtk3-git`
folder.
```bash
$ ls *.pkg.tar.xz
$ pacman -U "mingw-w64-{{{ VARIOUS SPECIFICS HERE }}}.pkg.tar.xz"
```
4. Test the installation using e.g. ``gtk3-demo`` {{< colour "yellow" >}}from the
``MINGW32`` or ``MINGW64`` shell.{{< /colour >}}
