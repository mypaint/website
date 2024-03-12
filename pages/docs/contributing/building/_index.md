+++
title = "Building"
related = ["../testing","/docs/backend/build-process"]
hideList = true
+++

Building MyPaint from source gives testers and developers the most bleeding edge
feature set MyPaint has to offer. For most use cases, the end user will not need
this guide: MyPaint is packaged in Flathub, as an AppImage, and in many popular
distributions.<!--more-->

{{< button content="Windows Build Environment" href="windows"
src="/icons/brands/windows.svg" >}}

# First Party Dependencies
These dependencies are developed by the MyPaint project.

{{< button content="Building libmypaint" href="libmypaint" >}}
{{< button content="Building MyPaint Brushes" href="brushes" >}}

## User Installation
You don't need to install first party dependencies in user directories (i.e. not
system-wide) in order to install MyPaint as a user, but if you want to, use the
following pattern:
```console
./configure --prefix=$BASE_DIR && make install
```

# Third Party Dependencies
MyPaint depends on the following software:
- python (>= 2.7.4)
- gtk3 (>= 3.12)
- pygobject
- setuptools
- swig (>= 3)
- numpy
- librsvg2 (and its svg gdk-pixbuf loader)
- pycairo (>= 1.4)
- lcms

## Debian-based
```console
sudo apt-get install -y \
git swig gettext g++ gir1.2-gtk-3.0 libgtk-3-dev libpng-dev liblcms2-dev \
libjson-c-dev python-gi-dev librsvg2-common

sudo apt-get install -y \
python3-setuptools python3-dev python3-numpy python3-gi-cairo
```

If this doesn't work, try older names for the development packages, such
as `libjson0-dev`, or `libpng12-dev`.

## Red Hat-based
```console
# yum install -y git swig gettext gcc-c++ libpng-devel lcms2-devel json-c-devel \
gtk3 gtk3-devel gobject-introspection pygobject3-devel \
librsvg2

# yum install -y python3-setuptools python3-devel python3-numpy
```

## SUSE-based
```console
# zypper install \
git swig gcc-c++ gobject-introspection gtk3-devel libpng16-devel liblcms2-devel \
libjson-c-devel librsvg-2-2 gettext-tools

# zypper install \
python311-setuptools python311-devel python311-numpy-devel python311-pycairo \
python311-gobject-devel
```
## MSYS2 (Windows)
For 32-bit targets, replace ``x86_64`` with ``i686``.
```console
pacman -S --noconfirm --needed \
git mingw-w64-x86_64-toolchain mingw-w64-x86_64-pkg-config \
mingw-w64-x86_64-python2-numpy mingw-w64-x86_64-gtk3 \
mingw-w64-x86_64-pygobject-devel mingw-w64-x86_64-lcms2 mingw-w64-x86_64-json-c \
mingw-w64-x86_64-librsvg mingw-w64-x86_64-hicolor-icon-theme \
mingw-w64-x86_64-python2-cairo mingw-w64-x86_64-python2-gobject \
mingw-w64-x86_64-mypaint-brushes2
```

## MacPorts (macOS)
```console
export PKG_CONFIG_PATH=/opt/local/Library/Frameworks/Python.framework/Versions/3.11/lib/pkgconfig/
export CFLAGS="-I/opt/local/include"

sudo port install gtk3
sudo port install json-c
sudo port install lcms2
sudo port install hicolor-icon-theme
sudo port install librsvg

sudo port install py311-numpy
sudo port install py311-scipy
sudo port install py311-pyobjc-cocoa # optional, for i18n support
sudo port install py311-gobject3
```

# Build MyPaint
MyPaint is a Python project, and contains a `setup.py` script in the repo's root
directory. However, this isn't a typical Python module, so `pip install` doesn't
work.

```console
python setup.py --help-commands   # list all commands
python setup.py --help build   # get options for "build"
```

## Demo Mode
Run MyPaint without leaving behind build artefacts. Settings aren't saved between
runs.
```console
python setup.py demo
```

## Managed Install/Uninstall
MyPaint has an additional custom install command, for people used to our old SCons
recipes. It isn't compatible with SCons installs, but it allows you to do an uninstall
later.

```console
# For most Linux types
sudo python setup.py managed_install
sudo python setup.py managed_install --prefix=/usr

# You may need to make data files world-readable if you use "sudo"
sudo find /usr/local -ipath '*mypaint*' -exec chmod -c a+rX {} \;

# You can uninstall at any later time
sudo python setup.py managed_uninstall
sudo python setup.py managed_uninstall --prefix=/usr
```

Note that uninstallation doesn't get rid of all the folders that the managed install
created.

### Changing Install Directory
The default install location is `/usr/local`. To change this, use the ``--prefix``
option:
```console
python setup.py managed_install --prefix="/PATH/TO/DIR/"
```

## pkgconfig
If ``setup.py`` can't locate your pkgconfig path, use the ``PKG_CONFIG_PATH`` environment
variable, e.g.
```console
export PKG_CONFIG_PATH=/PATH/TO/lib/pkgconfig/:/PATH/TO/LIB/share/pkgconfig/
```
- The two colon-separated paths refer to the locations of package configuration
files for libmypaint and mypaint-brushes respectively.

In addition to knowing where libmypaint is installed when building,
MyPaint also needs to know its location when running:
- Run the ``build_ext`` command with the `--set-rpath` flag prior to installation.
    - {{< colour "yellow" >}}Remember to use the same prefix if uninstalling via
``managed_uninstall``{{< /colour >}}
- {{< colour "red" >}}(Not recommended){{< /colour >}} Use the ``LD_LIBRARY_PATH`` environment.
```console
python setup.py build_ext --set-rpath managed_install --prefix=$BASE_DIR

#If you want to build an older version of MyPaint that did not have this
#option, you can instead use the built-in `--rpath=` option to `build_ext`,
#setting the dependency path(s) manually.

python setup.py build_ext --rpath=$BASE_DIR/lib/
```
If you have already run the build script without `--set-rpath`,
you can run the following to force a rebuild:
```console
python setup.py build_ext --set-rpath --force
```

## Custom installation directory layout
The directory layout of MyPaint installations is specified in ``setup.cfg`` (TOML),
in the ``[install]`` table.

In those paths, ``$base`` is a placeholder that is replaced by the value set with
**`--prefix`** in the install command (**`/usr`** by default).

The installation directories can be overridden for each type by providing a flag
to the **`install`** command equivalent to the name of one of the `install-xyz`
variables in **`setup.cfg`**. For example:

```
python setup.py install --prefix=/usr/local --install-purelib='$base/lib64/mypaint'
```

# Run MyPaint
The start script `mypaint` will be placed in `$BASE_DIR/bin/`, so either add that
path to your PATH environment variable:
```console
export PATH=$BASE_DIR/bin/:$PATH
mypaint
```

or create links to the script:
```console
ln -s $BASE_DIR/bin/mypaint my-local-mypaint
./my-local-mypaint
```
