+++
title =  "Development Activity is Moving to Github"
author = "Andrew Chadwick"
date =   2014-07-22T00:00:00Z
tags = ["legacy"]
+++

In just under a week’s time, on Sunday 27th July 2014, I’ll be moving MyPaint’s
[old Gitorious git repositories][gitorious] over to the [new GitHub ones][github]
fully, and closing down the old location. For a while now we’ve been maintaining
the codelines in parallel to give people some time to switch over and get used to
the new site; it’s time to formally switch over now.

[gitorious]: https://gitorious.org/mypaint/
[github]: https://github.com/mypaint

If you haven’t yet changed your remotes over on existing clones, now would be a
very good time to do that!

The bug tracker is moving from [Gna!][gna] to Github’s issues tracker too – albeit
rather slowly. This is less a matter of just pushing code to a new place and telling
people about the move; rather we have to triage bugs as we go, and the energy and
will to do that has been somewhat lacking of late. Bug triage isn’t fun, but it
needs to be done.

[gna]: https://gna.org/bugs/?group=mypaint

(Github’s tools are lovely, and we’re already benefiting from having more eyeballs
focussed on the projects. [libmypaint][libmypaint] has started using Travis and
Appveyor for CI, the MyPaint application’s docs will benefit tons from being more
wiki-like to edit, and the issue tracker is just frankly better documented and
nicer for pasting in screencaps and exception dumps)

[libmypaint]: https://github.com/mypaint/libmypaint
