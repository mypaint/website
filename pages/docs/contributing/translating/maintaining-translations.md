+++
title = "Maintaining Translations"
+++

# Writing Localisable Python
- Localize any string presented to the user in the GUI.
- Always provide contexts for translators.

We have a [custom gettext module][mypaint-gettext] which you can import for translation
functions that resemble the C gettext macros. For new code, please always provide
contexts. The context string can be a `str` literal, and while we're using Python 2.7
at least, it's visually helpful to write `unicode` literals for the source string.

```python
label.set_text(C_(
    # Context string:
    "some module: some dialog: label",
    # Source string ("msgid") to be translated:
    u"Long Unicode message to be translated. "
    u"Our source language is US English. "
    u"You can use formatting codes here, “{like_this}”."
)).format(
    like_this = "just like this",
)
```

They have to be used almost as if they were actual C macros, meaning you must write
the strings in the `C_()` call as literals. However `intltool` knows about Python
constructs and formatting codes.

Favour standard US English punctuation for new translated strings, and use proper
Unicode punctuation like `“…’–”` instead of `"...'-`.

The practicalities of quoting things like filenames for the user to see mean that
it's better to use double curly quotes in preference to single quotes. They're easier
to see, and the user is more likely to have filenames with apostrophes in them.
Also, please place punctuation outside the final quote.

[mypaint-gettext]: https://github.com/mypaint/mypaint/blob/master/lib/gettext.py

# Weblate
_This document is only intended to cover the basics that devs and maintainers should
know about how to work with Weblate translations. For detailed and comprehensive
information about everything else, see the [Weblate documentation](https://docs.weblate.org/en/latest/)_

Weblate handles translations by maintaining an internal state for contributions
by different users that is periodically turned into commits to a clone of the git
repository of the project the translations apply to (in this case, mypaint and libmypaint).

For each project, the address of this repository can be found under the **Info** tab on the line marked **Repository containing Weblate translations**.
For the mypaint repository, the repo address is (at the time of writing) `https://hosted.weblate.org/git/mypaint/mypaint/`


## Fetching the repo
_In these examples, we are working on translations for the mypaint repo. The principle is exactly the same for libmypaint or other projects using weblate for translations._

There are two basic ways of setting up your repositories to work with the translation commits: either adding the weblate project repo as a remote to your clone of the mypaint repo, or cloning the weblate repo separately.

_Cloning the weblate repo_
```
# It can be a good idea to rename the destination, in this case to weblate-mypaint
# to separate the translation clone from the "original".
git clone https://hosted.weblate.org/git/mypaint/mypaint/ weblate-mypaint
```
_Adding the repo as a new remote_
```
# 
cd /wherever/my/mypaint/repo/is/mypaint
git remote add weblate https://hosted.weblate.org/git/mypaint/mypaint/
git fetch
```

## Merging and pushing translations
Most of the time, simple merges are enough. 

If you created a clone of the weblate repo, you can push it to a new repo under your own github account and create a pull request using the gui.

If you added the repo is a remote instead, have push access to master, and are *quite certain* that the changes are ok, you can also merge and push directly:

```
git checkout master
# Assuming the weblate/master branch is up to date
git merge weblate/master
# Assuming the merge completed without any issues, that master tracks correctly etc.
git push
```

## Rebasing translations
***If you don't have admin access to the weblate account, don't push rebased commits until you can get a hold of someone who does have access and coordinate the changes with them!***

Rebasing the translation commits can be useful for getting rid of the numerous merge commits that can end up in the translation repo over the course of development. It can also be useful when manual editing is required due to some file conflicts or unwanted changes.

*However*, pushing rebased translations requires the weblate repo to be reset to the HEAD of the updated branch it is tracking. If it is not reset, commits will be duplicated and things will be generally messed up.

### Rebasing using the weblate interface
If you have administrative access to the project on weblate, you have access to a menu called **Manage** under the component pages, e.g. https://hosted.weblate.org/projects/mypaint/mypaint . Under that menu, there is an option called **Repository Maintenance**, which leads to a page with a number of controls. For simple rebasing where we only want to get the commits in one consecutive chunk on top the current master HEAD, just clicking the **Rebase** button should be enough. The changes can then be merged as described in the previous section.

### Rebasing manually

If you need more control of the rebasing process - for squashing/removing/editing particular commits - you should use either a clone of the weblate repo or working in a new branch based on an up-to-date version of the weblate master branch.

When your rebase is ready, either set up a pull request that clearly states that it is a rebase of translation commits, or if you have admin access to the weblate project, you can push to master but immediately (reasonably immediately) follow up the push by pulling and resetting (by pressing on **Pull** and then **Reset**) on the same **Repository Maintenance** page that holds the **Rebase** option.
