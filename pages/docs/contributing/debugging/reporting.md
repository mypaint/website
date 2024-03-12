+++
title = "Reporting Issues"
+++

> :rage: _Something gone wrong?_ Report new bugs in the [Issue Tracker][tracker]  
> :rabbit: _Go deeper:_ see [[Fixing Bugs]]  
> :books: This page is part of a series on [[how you can take part in the MyPaint project|Contributing]]  

All bugs and related issues are public,
and can be searched in the issue trackers for the two main projects
([MyPaint][code.mypaint], [libmypaint][code.libmypaint]).
We also have a dedicated [developer's discussion forum][code.forum]
for those wanting help or a place to chat.


[code.mypaint]: https://github.com/mypaint/mypaint/issues
[code.libmypaint]: https://github.com/mypaint/libmypaint/issues
[code.forum]: http://community.mypaint.org/c/development

### Before reporting

* Try to make sure the problem you're seeing really is a bug!  
  A mistake from installing, corrupt files, and interactions with other software can all seem like bugs in MyPaint.
* Look in the [[Frequently Asked Questions (FAQ)|FAQ]] list to see if your problem has already been reported.
* If this is your first time posting a bug on our Issue Tracker, or if you are not sure if it is a bug, we strongly recommend you first post it our [Community Forums](#mypaint-community-forums).
* Please report bugs against the newest version of MyPaint you can find.
  * MyPaint 1.0.0 is not supported. If you are on Windows, much more up-to-date builds are available:
  * :package: <https://github.com/mypaint/mypaint/releases>

## How to report an issue on our Github Issue Tracker

1. **Click on the Issues tab** on the project page.

   > ![issues tab in context](https://cloud.githubusercontent.com/assets/61299/12677480/45a6c104-c691-11e5-9483-10bc6f9f4cf0.png)

2. **Search for your issue**. Somebody may already have reported it!

  > ![Filtering and search bar](https://cloud.githubusercontent.com/assets/61299/12677191/1ae49614-c68f-11e5-8c7b-3f24a2da933f.png)

  Press `Return` to search the tracker. You'll see `is:open` in the search box by default. The `is:open` keyword limits the results to just open issues, so it's a good idea to remove before when searching. Your issue may already have been fixed and closed.

3. **Click the “New Issue” button**, then fill in the form that appears.

4. **Fill in a good title**.
  If you're not sure how to write a good title, use a pattern like “\<feature\>: \<what-went-wrong-with-it\>”.
  Avoid titles like “Problem”, or “Can't do \<thing\>”. The title should explain _how_ it went wrong if possible.

5. **Fill in the body of the report in detail**. Detail is good. It's important to mention quite a few things:
   > ![Filling in the form (animated gif)](https://cloud.githubusercontent.com/assets/61299/12676285/c6cc7782-c688-11e5-8937-0cda2b47a4b6.gif)

  * A brief description of the problem, expanding on what's in the title.
  * The version of MyPaint you saw the problem in, and details of your operating system.
  * The full texts of any error messages you saw.
  * Anything you tried to work around the problem.
  * Most importantly: full steps telling us how *we* can reproduce the problem!

  We use a [template](https://github.com/mypaint/mypaint/blob/master/ISSUE_TEMPLATE.md) now. Hopefully all you will need to do is fill in the headed sections. :smile:

6. **Click the “Submit New Issue” button**.

  Your report will then be visible to everyone looking at the issue tracker, and hopefully somebody will respond to it soon. [How we handle most bug report are described here](#how-we-will-handle-your-bugs-reports-and-user-support-threads).

## Opening a User Support Thread on our Community Forums

1. **Click on the User Support** option under the "all categories" dropdown menu at the top of the Community Forums Front Page.

2. **Search for your question or topic** before you post. Somebody may already have reported it!

  * If you click on the search icon at the top of the page while in the User Support Category, searches will limit to just the user support category. Uncheck the option below the text box to search the site globally.

3. **Click the “New Topic” button**, then fill in the topic template, and follow its instructions.

4. Fill out the topic template, and follow its instructions.
  * Please keep in mind our [reporting guidelines](#reporting-guidelines) and Community Forums [FAQ Page](https://community.mypaint.org/faq) when filling it out.

5. **Give it a good title**.
  * For our Community forums, it a good idea to either form your topic as a question, or state the problem and/or task you wish to accomplish.

6. **Click the “+ Create Topic” button**.

  Your report will then be visible to everyone looking at the issue tracker, and hopefully somebody will respond to it soon. [How we handle most of our user support topics are described here](#how-we-will-handle-your-bugs-reports-and-user-support-threads).

## Reporting guidelines

When reporting a new bug or starting a User Support Thread,

* Stay on topic.
  * Please limit your issue reports to a single, fixable problem.
  * Do not piggyback issue reports.
* When reporting a bug, try to be specific.
* Give your new report a good title, so it can be found easily in a list, and easily search for.
* In the title field, explain briefly what component went wrong, and how it went wrong.
* Make the first paragraph a concise summary without speculating too much.
* Make sure to include detailed information which can help in pinpointing and fixing the bug.
* Include the steps you know of to reproduce the bug.
* Include what happens when the bug appears.
* In-program bug reports, error messages, and strange program behaviour are all good info to provide.
* Share what you expect to happen and what _actually_ happens.
* Paste in the _exact_ version of MyPaint. Either of the following will do:
  - The detailed version number pasted in from **Help → About MyPaint**. This looks like `1.2.1` for normal releases, or something longer like `1.2.0-beta.3.111+git.e0faa7f` for prereleases.
  - The long hexadecimal string from `git log`, if you're a developer. The one that looks like `e0faa7f07ccdfdc43180c2b33c6a46d6f9e609fa`.
* Also include your operating system and its version number, and whatever other information seems related to the bug. For example, always include your tablet brand and model name/number when reporting a problem with input handling.
* A picture is often worth a thousand words - and a screencap can be dragged into a report for us to look at.

Here's an example of a [helpful bug report](https://web.archive.org/web/20150311214529/https://gna.org/bugs/?func=detailitem&item_id=17613#comment0) from our old tracker.

If you are requesting a new feature, please submit mockups, pictures, or other clear explanations of what it is you want. And please tell us how the feature would help you. If you want community input on the feature you want, post it on our Community Forums under the [Feature Request Category][feature-request]. 

## How we will handle your Bugs Reports and User Support threads.

### Github Issue Tracker
> :link: See also [[Answering Issues]]

The Github Issue Tracker is where the bulk of our bugs are filed and are waiting to be fixed. If you follow our [guidelines](#reporting-guidelines), and fill out the issue tracker template completely and accurately, our developers and contributors can easily address and potentially fix the bug. If not, we will ask you questions that need to be answered before we can continue. If one of our developers or contributors can duplicate the bug, we should be able to get a fix out in a timely matter. If not, we may ask you to [Build MyPaint][build] from source to see if the bug is fixed. Don't worry if you cannot build MyPaint. We have places like our [User Support Chatroom on our Community Forums][chat] where we can walk you through the process if need be.

Don't be discourage if the issue gets closed when there is nothing we can do about it in the current phase of development or if the thread becomes stale. In those cases we will review them at a later time and open a new issue thread that is fresh and refer back to the original report when possible.

### User Support Threads

As far as standard user support requests and questions about MyPaint go, our Github Issue tracker is not really intended for such use case. For those kind of threads, we strongly encourage you post it on our [Community Fourms](#mypaint-community-forums) first. If the issue you posted on the Github Tracker turns out to be a user support, don't worry, we can sometimes help investigate your problems there. Your problem report my turn into a workaround you can use which we can share with other MyPaint users on our Community Forums. Many of these User Support threads have help us uncover a more fundamental bug in the program code or external program code we rely on. [GTK](https://developer.gnome.org/gtk3/3.0/gtk.html) for example is one such library we use for MyPaint's Graphic User Interface(GUI) and a lot of the Graphic Tablet/Touchscreen's centric features.

### MyPaint Community Forums
> :link: Visit [MyPaint Community Forums][community]

If this is your first time reporting a bug, or if you unsure if it is a bug, or if you have a question about MyPaint which is not on our [[Frequently Asked Questions (FAQ)|FAQ]], we strongly recommend you to post it our our Community Forums [User Support Area][support] first. This will allow us to help you investigate the problem and help you solve it. If the problem turns out to be a bug within MyPaint, we will help you produce a rock solid bug report which our developers and contributors can tackle. If it turns out to be a bug in a library that MyPaint relies on, we will help you report a bug on their bug tracker as well. Once the bug report is filed, we'll link it back on the original user support thread. This will allow other users who may have the same problem be up-to-date on it as well.

If one of our Moderators or Staff on the MyPaint Community Forums changes the title, the content, adds tags or moves your thread to another category, don't worry. We just want to help keep our Community Forums organized and easy for users to navigate. If such a thing were to happen on your thread, we will be sure to notify your thread of the changes and our reasoning behind those changes. The changes made to the content of the post will also be in the edit history which is an orange pencil icon at the top right-hand part of your post.

### See Also

* [[Fixing Bugs]]
* [[Debugging Tablet Issues on Windows]]

[tracker]: https://github.com/mypaint/mypaint/issues
[community]: https://community.mypaint.org
[support]: https://community.mypaint.org/c/support
[build]: https://github.com/mypaint/mypaint/blob/master/README.md#build-and-install
[chat]: https://community.mypaint.org/chat/support/623
[feature-request]: https://community.mypaint.org/c/feature-requests
