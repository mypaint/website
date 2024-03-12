+++
title = "Building libmypaint"
+++

MyPaint's brush engine, [libmypaint][libmypaint] is a discrete
external library to MyPaint.<!--more-->

When building a branch/tag of MyPaint, build the corresponding branch of libmypaint.
- e.g. ``MyPaint/main`` with ``libmypaint/main``
- When building old commits of MyPaint, search for `libmypaint` using `git log`,
then infer the corresponding libmypaint commit by cross-referencing the commit logs.

[libmypaint]: https://github.com/mypaint/libmypaint

# Dependencies
- All configurations and builds:
  - [json-c](https://github.com/json-c/json-c/wiki) (>= 0.11)
  - C compiler, `make` etc.
- Most configurations (all except `--disable-introspection --without-glib`):
  - [GObject-Introspection](https://live.gnome.org/GObjectIntrospection)
  - [GLib](https://wiki.gnome.org/Projects/GLib)
- When building from `git` (developer package names vary by distribution):
  - [Python](http://python.org/)
  - [autotools](https://en.wikipedia.org/wiki/GNU_Build_System)
  - [intltool](https://freedesktop.org/wiki/Software/intltool/)
  - [gettext](https://www.gnu.org/software/gettext/gettext.html)
- For `--enable-gegl` (GIMP *does not* require this):
  - [GEGL + BABL](http://gegl.org/)

## Debian-based
```console
# apt install -y build-essential
# apt install -y libjson-c-dev libgirepository1.0-dev libglib2.0-dev
```
When building from git:
```console
# apt install -y python autotools-dev intltool gettext libtool
```
## Red Hat-based
```console
# yum install -y gcc gobject-introspection-devel json-c-devel glib2-devel
```
When building from git:
```console
# yum install -y git python autoconf intltool gettext libtool
```
## SUSE-based
```console
# zypper install -t pattern devel_basis
# zypper install gcc13 gobject-introspection-devel libjson-c-devel glib2-devel
```
When building from git:
```console
# zypper install git python311 autoconf intltool gettext-tools libtool
```

# Build libmypaint

## Optimization Flags
MyPaint and libmypaint benefit dramatically from autovectorization and other compiler
optimizations. You may want to set your CFLAGS before compiling:
```console
export CFLAGS='-Ofast -ftree-vectorize -fopt-info-vec-optimized -march=native -mtune=native -funsafe-math-optimizations -funsafe-loop-optimizations'
```
{{< colour "yellow" >}}To avoid potential glitches, make sure to compile both libmypaint
and MyPaint using the same optimization flags.{{< /colour >}}

## Steps
The traditional setup works just fine.

    $ ./autogen.sh    # Only needed when building from git.
    $ ./configure
    # make install
    # ldconfig

### Maintainer mode

We don't ship a `configure` script in our git repository. If you're
building from git, you have to kickstart the build environment with:

    $ git clone https://github.com/mypaint/libmypaint.git
    $ cd libmypaint
    $ ./autogen.sh

This script generates `configure` from `configure.ac`, after running a
few checks to make sure your build environment is broadly OK. It also
regenerates certain important generated headers if they need it.

Folks building from a release tarball don't need to do this: they will
have a `configure` script from the start.

### Configure

    $ ./configure
    $ ./configure --prefix=/tmp/junk/example

There are several MyPaint-specific options.
These can be shown by running

    $ ./configure --help
|Action|Command|
|:-|:-|
|Build|``$ make``|
|Test (run unit tests)|``$ make check``|
|Install|``# make install``|
|Uninstall|``# make uninstall``|

# Check Availability
Make sure that pkg-config can see libmypaint before trying to build with it.
```console
$ pkg-config --list-all | grep -i mypaint
```

If it's not found, you'll need to add the relevant pkgconfig directory to
the `pkg-config` search path. For example, on CentOS, with a default install:
```console
# sh -c "echo 'PKG_CONFIG_PATH=/usr/local/lib/pkgconfig' >>/etc/environment"
```

Make sure ldconfig can see libmypaint as well
```console
# ldconfig -p |grep -i libmypaint
```

If it's not found, you'll need to add the relevant lib directory to
the LD_LIBRARY_PATH:
    
```console
$ export LD_LIBRARY_PATH=/usr/local/lib
# sh -c "echo 'LD_LIBRARY_PATH=/usr/local/lib' >>/etc/environment
```

Alternatively, you may want to enable /usr/local for libraries.  Arch and Redhat derivatives:
```console
# sh -c "echo '/usr/local/lib' > /etc/ld.so.conf.d/usrlocal.conf"
# ldconfig
```

# Make Release
The distribution release can be generated with:

```console
$ make dist
```

And it should be checked before public release with:

```console
$ make distcheck
```

# Localisation

Contribute translations here: <https://hosted.weblate.org/engage/mypaint/>.

The list of languages is maintained in [po/LINGUAS](po/LINGUAS).
Currently this file lists all the languages we have translations for.
It can be regenerated with:

```console
$ ls po/*.po | sed 's$^.*po/\([^.]*\).po$\1$' | sort > po/LINGUAS
```

You can also disable languages by removing them from the list if needed.

A list of files where localizable strings can be found is maintained
in `po/POTFILES.in`.

## Strings update

You can update the .po files when translated strings in the code change
using:

```console
$ cd po && make update-po
```

When the results of this are pushed, Weblate translators will see the
new strings immediately.
