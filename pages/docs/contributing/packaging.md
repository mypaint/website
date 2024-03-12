+++
title = "Packaging"
+++

We are always open for more people willing to maintain buildsfor Mac 
OS X, Windows, or Linux distributions.If you want to help us port 
MyPaint to your OS or Linux Distribution,please visit our community 
forums under the [Porting MyPaint Category][source.porting], and ask away 
there.You can also ask questions there if you are having trouble 
building MyPaint.

[source.porting]: http://community.mypaint.org/c/development/porting

### Packaging
Get official source tarballs
from the [releases page][packing.releases] on Github.
Most packages should be built from these.

Our [Packaging][packing.wiki] wiki page is a catalogue of all the
ongoing packaging efforts we know about,
including those made by third parties.
If you intend to start a new packaging project,
please tell us about it and link it on the wiki.

We're also looking for people willing to maintain builds
for Mac OS X and Windows.
It helps having a person familiar to the platform they're building on.

See the [main README file][packing.readme] for details of
how to build MyPaint from source across a variety of platforms.
If you have questions, or want to port MyPaint to
Mac OS X, Windows, another Linux distribution, please vist our Community
forums under the [Porting MyPaint Category][packing.porting],
and ask away there.

[packing.releases]: https://github.com/mypaint/mypaint/releases
[packing.wiki]: https://github.com/mypaint/mypaint/wiki/Packaging
[packing.readme]: https://github.com/mypaint/mypaint/blob/master/README.md
[packing.porting]: http://community.mypaint.org/c/development/porting

### Existing packaging projects

* MyPaint has a canonical source tarball available for each release we make. You can find them on our github [releases page](https://github.com/mypaint/mypaint/releases).
* You'll also find Windows installer binaries there, built by [@achadwick](https://github.com/achadwick).
* Ubuntu Linux testing PPA: <https://launchpad.net/~achadwick/+archive/ubuntu/mypaint-testing>, built by [@achadwick](https://github.com/achadwick)
* MyPaint stable binaries are distributed with many Linux distributions in binary form.
* Mac OS X Homebrew: <https://github.com/mypaint/mypaint/issues/346>
* Mac OS X Macports: <https://www.macports.org/ports.php?by=name&substr=mypaint>
* Windows MSYS2 (stable) <https://github.com/Alexpux/MINGW-packages/tree/master/mingw-w64-mypaint>
* Windows MSYS2 (git) <https://github.com/Alexpux/MINGW-packages/tree/master/mingw-w64-mypaint-git>

### New packaging projects

Firstly, please feel free to link to your project above.

I'm happy to accept packaging/build scripts for well-known, and well-defined platform distributions like Homebrew/Fink/MacPorts on Mac, MSYS2/MSYS/Cygwin on Windows, or Fedora/Arch/BigDistrib on Linux. basically, if it has a package manager and you can write a build script or control file for it, I'm interested!

Normally, if the build script can slot into the main MyPaint project without upsetting third-party downstream builds, I'm happy to have the code reside in the [mypaint/mypaint](https://github.com/mypaint/debian) repository under a subdirectory which also contains instructions for the build. If it has more complex requirements (like our [mypaint/debian](https://github.com/mypaint/debian) one for the PPA, where the folder name would clash with official Debian builds), a separate module may be more useful.
