+++
title = "Brush Engine"
summary = "How MyPaint places content on the canvas"
mypaintver = "v3.0.0"
+++

# Brush engine
MyPaint brush functionality is separated in a C library called [libmypaint](https://github.com/mypaint/libmypaint) that can be used in other applications.
-   Brush dabbing, area filling, and layer compositing code is written in C++, as a python extension module
-   The C++ dialect is fairly standard, with some inline templating for code composition, and some use of STL
-   Some of the C code (brushsettings) is generated with Python

## First Order Lowpass Filter
They are used in many places in the brush code but most importantly to filter the velocity. This is how it is done when reacting to timestamped events:

    fac = exp(-dt/T1); output = fac*output + (1-fac)*input;

* `dt`: time passed since last calculation
* `T1`: time constant. After this time, about 2/3 of the difference between input and output is gone.

If the input is a position, then

    filtered_velocity = input - output

### Brush Observers etc.
[[Development-Documentation-Brush-observers.png]]

That's how it is currently (subject to change)
