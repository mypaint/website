+++
title = "Windows Porting"
author = "Andrew Chadwick"
date = 2015-07-19T00:00:00Z
tags = ["legacy"]
+++

I’m hoping that MyPaint will be able to support Windows fully starting with the
first v1.2.0-beta release. This is made possible by the efforts of our own Windows
porters and testers, and the dedicated folks who keep MSYS2 working so well.
- (image: The Inno Setup installer we'll be using starting with the 1.2.0-beta releases.)

Releases will start happening shortly (date TBA) on Github, and you’ll be able to
pull down installer binaries for 32 bit and 64 bit Windows as part of this.

If you’re interested in the workings of the installer build, and would like to test
it and help it improve, it’s all documented and scripted [in the current github
master](https://github.com/mypaint/mypaint/tree/master/windows). Please be aware
that SourceForge downloads are involved during the build procedure until MSYS2 fix
that. Our own binaries and installers will never be knowingly distributed – by us
– through SourceForge or any similar crapware bundling site.

