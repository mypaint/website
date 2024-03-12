+++
title = "Translating MyPaint"
+++

### Translating
Help MyPaint reach a more international audience
by helping us [translate it to your language][translate.wiki].
We use [Weblate][translate.weblate],
a free web-based translation management system,
to make it simpler for new translators to get started.

[translate.wiki]: https://github.com/mypaint/mypaint/wiki/Translating-MyPaint
[translate.weblate]: https://weblate.org/en/

> :globe_with_meridians: _Get translating:_ [log in to Weblate, and start translating MyPaint][tr].  
> :rabbit: _Go deeper:_ check out the [list of issues labelled “translation”][trissues].

MyPaint supports 30 languages at the time of writing. This excludes different spellings of English. Not every language is complete, but you can help us improve.

Translating the text that gets displayed on the screen is now much easier than before. Anyone who uses MyPaint regularly and has good language skills can help:

* Work on translations in [MyPaint's project pages on Weblate][tr].
* Read a brief tutorial describing how MyPaint gets translated: <http://mypaint.org/blog/2015/11/21/final-translation-push-for-1-2-0/>
* Our wiki documentation needs translating too: see [[Writing Documentation]] for details of how you can help.

In the run-up to a release, translations are frozen to give translators a chance to work on a consistent base text.
The translation README details the complete workflow in detail: [po/README.md](https://github.com/mypaint/mypaint/blob/master/po/README.md).

We use GNU gettext for i18n, and the language used in the source code is US English.


---
# Translator Crash Course

## Basics

A _source string_, also called original string, is a piece of text that is used somewhere in the program. When a particular language is used, the _source string_ is replaced with the corresponding _translation string_ for that language, if that string exists. If the _translation string_ does *not* exist, the _source string_ is used instead.

## Substitutions

There are a few things that should be left unchanged in your translations. For this section, we'll use the ancient language of double-vowel flipped-grammar English to illustrate examples.

### {brace_variables}
You will find many strings containing pairs of braces {} with characters in between.
In the user interface, these are replaced with words, numbers or other character sequences. You can place them wherever you need to, and if necessary they can be used in multiple places, but they **cannot be removed**.

**Example:**  
_Source string:_ `Remove the brush named {brush_name} from the list.`  
_Translation:_ `Froom the list, reemoovee thee bruush naameed {brush_name}.`  

### %s, %d

These serve the same purpose as brace variables, acting as placeholders that will be replaced in the final output. They have a couple of disadvantages compared to the brace variables: they don't communicate what the nature of the substitution is and more importantly, _they cannot be reordered_. For these reasons, these variables only occur in old strings, and only 20 out of 1265 (currently) strings make use of them (and at most once per string).

**%s** - This will be replaced by a string  
**%d** - This will be replaced by an integer (like 12, -4, 2, not 0.34 or 45.23)  

**Example:**
_Source string:_ `Moved brush to category %s.`  
_Translation:_ `Too caateegooryy %s, bruush waas mooved.`  

## General guidelines

* **Try to be consistent**  
There is a lot of terminology in MyPaint, and some it can be hard to translate. Even if you don't find the perfect word or phrase in your own language, try to make sure that you use that word or phrase consistently. Make use of the glossary in Weblate to try to make sure that other translators of your language are on the same page, and coordinate with them by using the translator comments if you feel uncertain.

* **Don't limit yourself by the grammar of the source strings**  
The purpose of text in the user interface is to be instructive and informative. What is important is that the text is _understandable and correct_ in terms of _what it describes_, not that it follows the grammatical structure of the source string. If you don't understand what the text actually describes (there are many strings where this is not made clear), please ask for clarification in a "Source string comment" in the Weblate interface.

* **Don't rush**  
Your translations do not have to be perfect the first time around. You can go back and change a translation at any point. Creating good translations is not easy!

Thus ends the Translator Crash Course

---

# Crediting your work

There is a special source string `translator-credits` that is used to credit the translators of a particular language in the About MyPaint dialog. This string should not be translated literally, but instead simply contain a list of names, optionally with email addresses and years (or year ranges) indicating when they contributed to the translations. If you have contributed to the _translation_ of a language, either in MyPaint or libmypaint, you may add yourself to this list (it is not required, but encouraged).

Each name should be on its own line, and each line should have one of the following structures:

* _name_
* _name_ <_email_>
* _name_ <_email_>, _year-of-contribution_
* _name_ <_email_>, _year-of-first-contribution_-_year-of-most-recent-contribution_

Email can be omitted for the last two examples as well.

> :information_source:  
> The message string should only contain a list of names. There should be no leading "Translators:" or such,
> the about dialog takes care of that for you.

[tr]: https://hosted.weblate.org/engage/mypaint/
[trissues]: https://github.com/mypaint/mypaint/issues?q=is%3Aopen+is%3Aissue+label%3Atranslation
