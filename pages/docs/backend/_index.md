+++
title = "Backend Documentation"
summary = "Developer guides and reference for MyPaint's backend code"
+++

This section concisely describes fundamental aspects of the project's technology,
including files and technical concepts to help developers conceptualise MyPaint.
The most detailed documentation for the project will always be contained within
the source code.<!--more-->

# Contributor Responsibilities
- Please write code that matches what you see elsewhere. [Style guide]({{< ref "../contributing/style-guide" >}})
- [Git workflow]({{< ref "../contributing/git" >}})
- Contributed code must abide by our [Licensing Policy]({{< ref "../contributing/licenses" >}})
- [Keep these docs up to date]({{< ref "../contributing/documentation#developer-documentation" >}})
- [Documenting your code properly]({{< ref "../contributing/documentation#python" >}})

# Technology Overview
Here is a simplified (and somewhat outdated, sorry!) module dependency overview
(some "weak" dependencies are not shown):

```mermaid
requirementDiagram
requirement test_req {
    id: 1
    text: the test text.
    risk: high
    verifymethod: test
}

element test_entity {
    type: simulation
}

test_entity - satisfies -> test_req
```

![Less simplified version](modules-complex.png)

# Tooling
MyPaint (the painting application) is written in Python. MyPaint uses GTK for its
user interface, some of the more complicated bits are designed in Glade. Some parts
are coded in C++ for speed. Its brush engine is written as a portable C++ library.
- [Building]({{< relref "build-process" >}}), Testing, & Packaging
    - Setup.py uses distutils
    - Tests use nose
    - GitHub actions for CI
- [GUI]({{< relref "gui" >}})
    - PyGObject (PyGI)
    - Parts of the GUI are constructed in GLADE, other parts in the Python code
- [Canvas]({{< relref "canvas" >}})
    - NumPy
    - Cairo
- [Brush engine]({{< relref "brush-engine" >}})
    - libmypaint

## Windows
MyPaint uses [MSYS2](https://msys2.github.io/) for porting onto the Windows platform.

# Pages in this Section
