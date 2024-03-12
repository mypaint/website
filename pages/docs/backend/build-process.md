+++
title = "Build Process"
related = "/docs/contributing/building"
+++

MyPaint's build system is due to be replaced. Currently, the MyPaint application
is built with [PyPa][pypa]'s [``setuptools``][pypa-setuptools], with heavy utilisation
of [distutils][pypa-distutils]. The entry point to building MyPaint is [``setup.py``][st-setup-py],
configured by [``setup.cfg``][st-setup-cfg]. This page details how MyPaint's source
code is transformed into a working application.<!--more-->

The brush engine and some parts of the main program are written in fast C code, so they will need compiling.

[pypa]: https://www.pypa.io/
[pypa-setuptools]: https://setuptools.pypa.io
[pypa-distutils]: https://github.com/pypa/distutils
[st-setup-py]: https://setuptools.pypa.io/en/latest/references/keywords.html
[st-setup-cfg]: https://setuptools.pypa.io/en/latest/userguide/declarative_config.html

# Demo
Following what happens when running the command ``python3 setup.py demo`` gives
insight into the building process; The ``demo`` argument chains together each step
from start to finish:

1. Run ``python3 setup.py demo``, which calls
2. ``Demo(Command)``
    - Inherits distutils' [``Command``][stCommand]
    - Function/class calls in the proceeding lowest-level list items are done so
from this class.
3. Boilerplate stuff
4. [``Build(build)``]({{< relref "#build" >}})
5. ``Install(install)``
    - Inherits distutils' [``install``][stInstall], which itself inherits [``Command``][stCommand]
6. ``demo_cmd``
    - Defined as [``build_scripts.executable``][stBuildScripts]

[stBuild]: https://github.com/pypa/distutils/blob/main/distutils/command/build.py#L18
[stCommand]: https://github.com/pypa/distutils/blob/main/distutils/cmd.py#L17
[stBuildExt]: https://github.com/pypa/distutils/blob/main/distutils/command/build_ext.py
[stBuildPy]: https://github.com/pypa/distutils/blob/main/distutils/command/build_py.py
[stBuildCLib]: https://github.com/pypa/distutils/blob/main/distutils/command/build_clib.py
[stBuildScripts]: https://github.com/pypa/distutils/blob/main/distutils/command/build_scripts.py
[stInstall]: https://github.com/pypa/distutils/blob/main/distutils/command/install.py#L182

# Build
1. ``Build(build)``
    - Inherits distutils' [``build``][stBuild], which itself inherits [``Command``][stCommand]
    - Function/class calls in the proceeding lowest-level list items are done so
from this class.
2. ``BuildConfig(Command)``
    - Creates the configuration file (src/lib/config.py)
3. [``build_ext``][stBuildExt]
4. [``build_py``][stBuildPy]
5. [``build_clib``][stBuildCLib]
6. [``build_scripts``][stBuildScripts]
7. ``BuildTranslations(Command)``
