+++
title = "UX/UI Specification"
+++

This section describes the totality of MyPaint's UX/UI, including the relationship
between specifications and the backend. It is the primary source of reference for
developers and designers when suggesting, discussing, and prototyping new user-facing
features for MyPaint.<!--more-->

{{< colour "yellow" >}}**This section is heavily in development**{{< /colour >}}

# UX/UI Philosophy
As MyPaint continues to grow and expand its feature set, the project needs to ensure
that using MyPaint is ***intuitive*** and ***simple***. The MyPaint program should:
- Let you *[scribble without thinking][mklink]*.
- Not feel bloated and confusing.

## MyPaint Should be Intuitive
MyPaint needs to read the end-user's intentions at each scale of UX design. All
users at any level of technical or artistic skill should be able to *work in flow*
without thinking about the program.

- Ideally users won't need to consult the manual after learning the fundamental
MyPaint workflow.
- Drawing with MyPaint should be fast for experienced users.
- UX at the *macro* level should have a coherent topography that the user can easily
memorise and navigate.
- UX at the *micro* level needs to work in a way that *makes sense* and is *useful*
to the end user.
- Frequent interactions should be *fast*: Measure speed in milliseconds,
consider all sensible inputs, and maximise legibility of information.

## Using MyPaint Should be Easy
MyPaint should make the act of drawing as simple as possible. This doesn't mean
that MyPaint shouldn't be technically complex, just that any technical complexity
should be presented to the user in a way that's simple for them.

- A new user should immediately know how find to every feature in MyPaint.
    - *Deduction test:* Get a new user, describe a feature to them, and ask
them where they might find it.
    - *Induction test:* The user wants to do something that is a capability of
MyPaint, but has never used the capability before. Can they find our implementation
of the capability?
- Even at its most complex, MyPaint's UI should not feel crowded or overwhelming.

## MyPaint Should be Accessible
MyPaint needs to scale to the needs and circumstances of different users, their
setups, and their workflows.
- The capabilities of MyPaint should scale with the needs of the user.
- Every part of the UI with few exceptions should be able to be moved or hidden.

[mklink]: https://web.archive.org/web/20080517111220/http://mypaint.intilinux.com:80/?page_id=3
[philosophies]: http://web.archive.org/web/20150908043943/http://mypaint.intilinux.com/?page_id=56

# Getting Started
MyPaint's main window is the entry point from which all user interaction takes place.
{{< grid columns="4fr 1fr" align="center" >}}
{{< img caption="MyPaint main window layout" src="main-window.png" alt="A simplified and labelled graphic of MyPaint's UI">}}
{{< md >}}
1. [Canvas]({{< relref "canvas" >}})
2. [Panels]({{< relref "panels" >}})
3. [Top toolbar]({{< relref "toolbar-top" >}})
4. [Bottom toolbar]({{< relref "toolbar-bottom" >}})
5. [Menubar]({{< relref "menubar" >}})
{{< /md >}}
{{< /grid >}}
## Concepts
Concepts do XYZ

# Pages in this Section
