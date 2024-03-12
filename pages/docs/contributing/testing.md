+++
title = "Testing"
related = "building"
+++

It's really helpful to us if lots of people build and test the MyPaint development
If more people go hunting for bugs,
the more certain it is they will be reported.
Tracking the “master” development branch can be fiddly,
and you need to be familiar with the Linux command line
or its equivalent on your platform.

> :tulip: _Get started:_ build from source, and try out new features early!  
> :rabbit: _Go deeper:_ report bugs you find, and maybe contribute patches and tweaks.

It's really helpful to us if lots of people
build and test the MyPaint development master directly.
If more people go hunting for bugs,
the more certain it is they will be reported.
Tracking the “master” development branch can be fiddly,
and you need to be familiar with the Linux command line
or its equivalent on your platform.

### Basic workflow

See the [BUILDING.md](https://github.com/mypaint/mypaint/blob/master/BUILDING.md) file
for general instructions, and also hints about how you should do things on different platforms.

1. **Install** the dependencies you need onto your computer.
   MyPaint relies on a lot of other programs and bits of code to work.
   This includes [_libmypaint_](https://github.com/mypaint/libmypaint), which you most likely also have to build from source.
2. **Clone** the MyPaint source repository into your own development copy.
   You’ll be keeping this clone up to date regularly to catch the newest changes.
   Your local builds of MyPaint happen in this folder.
3. **Build** the program.
   The brush engine and some parts of the main program are written in fast C code, so they will need compiling.
4. **Test** the results of the build.
   This can be done entirely within your cloned source tree.
   Generally you should test with throwaway fresh configurations,
   but if you’re brave you can
   run it against your regular program configuration instead.
5. **Report problems** you find, or fix them.
6. **Regularly update** your cloned source tree, to get new features as they’re added!

See [[Reporting Bugs]], [[Programming]], and [[Contributing Patches]] for the next steps.
The basic workflow above is also a good place to start
if you'd like to contribute [[artwork|Contributing Artwork]] for use in the program,
or for getting the understanding necessary for [[packaging Mypaint for new platforms|Packaging]].

