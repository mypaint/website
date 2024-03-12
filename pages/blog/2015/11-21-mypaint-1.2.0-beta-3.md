+++
title = "MyPaint 1.2.0-beta.3 Released"
author = "Andrew Chadwick"
date = 2015-11-21T16:55:10Z
tags = ["legacy"]
+++

A new beta is available for download and testing. Hopefully this will be the last
beta before the final 1.2.0 release. Binaries are available for Ubuntu and Windows
systems, and the release is available in source form too. MyPaint v1.2.0-beta.3
can be downloaded from its [release page on github](https://github.com/mypaint/mypaint/releases/tag/v1.2.0-beta.3),
or from the [MyPaint-testing PPA](https://launchpad.net/~achadwick/+archive/ubuntu/mypaint-testing).

# Changes since v1.2.0-beta.2
- Suppress redraws during load and save (mypaint/mypaint#468)
- Better reporting when loading layer data from a GdkPixbuf file fails, especially
relevant for external file editing (mypaint/mypaint#476)
- Translation updates
- Fix attempt for some multi-source based glitches (mypaint/mypaint#460, mypaint/mypaint#177),
needs testing.
- Fix out-of-range tilt values (mypaint/mypaint#460) Close a loophole allowing an
initialization race condition (mypaint/mypaint#485)
- Translations are optional for the Windows installer (mypaint/mypaint#348), as
a workaround.
    - The real fix for a bad translation is to **get involved**, and contribute
your time and knowledge to make a [**better translation**](https://hosted.weblate.org/engage/mypaint/)!
    - It's really easy to get translating: [How to contribute better translations to MyPaint](http://mypaint.org/blog/2015/11/21/final-translation-push-for-1-2-0/)
- Reposition Layer is now in the layer context menu in the layers panel (mypaint/mypaint#489)
- Fix an annoying bug in the accelerator map editor (mypaint/mypaint#497)
- Assorted Windows build fixes.

# Known issues
Mostly Windows tablet woes right now.
- Glitches aplenty for Genius/Monoprice/Ugee clone tablets. Some may be fixed in this beta.
- Some combinations of hardware and Wacom tablets make drawing unbearably laggy on Windows.

Unfortunately the "threadfun" build I was asking people to test for the last beta
hasn't worked out as well as I'd hoped. It's just not stable enough to go into master
yet (sorry!), and I don't want to delay the release for a Windows-specific bug
that doesn't even affect every user.

