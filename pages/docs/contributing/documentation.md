+++
title = "Writing Documentation"
+++

You can improve MyPaint by making instructions for people using and people making
it. Good documentation is vital for everyone. Any sort of improvement, including
fixing typos and improving readability, is greatly appreciated.<!--more-->

Want to help improve our documentation but don't know where to start? Our issue
tracker contains issues with the documentation.
{{< flex >}}
    {{< button content="User Documentation Issues"
href="https://github.com/mypaint/mypaint/issues?q=is%3Aopen+is%3Aissue+label%3Acat.docs.user" >}}
    {{< button content="Developer Documentation Issues"
href="https://github.com/mypaint/mypaint/issues?q=is%3Aopen+is%3Aissue+label%3Acat.docs.dev" >}}
{{< /flex >}}

# Blogs & User Guides
This is the meat and bones of the project's documentation efforts. Ensuring users
have a solid understanding of the MyPaint application's functionality through user
guides, and new versions through release notes is vital to a healthy version lifecycle.

## Tone and Writing Style
- Page titles and headings should be in title case.
- Write using language understandable by a 12 to 14 year old.
- The MyPaint project has contributors across the world, and doesn't prescribe the
use of any one dialect. As long as it's clearly understood by most English readers,
your preferred dialect of English is okay to use.
- Do not assume readers' level of technical or artistic skill.
    - Avoid using "just" or "simply" when giving instructions.

## Translation
If a page is complete, please consider translating it into other languages. MyPaint's
design documentation aims to be a single source of truth, so decidedlly *not* translating
it reduces overhead.

[Hugo's page on multilingual content](https://gohugo.io/content-management/multilingual/)

Please also consider [translating MyPaint (the program)]({{<relref "translating/adding-translations" >}}).

# Developer Documentation
As a MyPaint developer, you are entrusted to keep the project's developer documentation
up-to-date. Poor or missing documentation is an obstacle to new contributors, and
you can help combat this by writing documentation. If you are new to technical writing,
here are some resources to get you started:
- [MDN Web Docs' blog post][mdn-tech-writing]
- [Google's courses][google-tech-writing]
- [FreeCodeCamp's articles][fcc-tech-writing]

[mdn-tech-writing]: https://developer.mozilla.org/en-US/blog/technical-writing/
[google-tech-writing]: https://developers.google.com/tech-writing/
[fcc-tech-writing]: https://www.freecodecamp.org/news/tag/technical-writing/

## Backend
Backend docs exist for two reasons:

1. To act as a primer given to *new* developers so that they can get started as
quickly as possible. They're presented to the reader as:
    1. Here's a file/concept.
    2. This is the gist of what you need to know.
    3. You're now prepared to read through the code and understand the specifics.
2. To help scope files/directories by describing them.

The most detailed documentation for the project will *always* be contained within
source code.

## UX/UI
GUI changes are drafted in the docs, and then applied per those specifications in
the program.

# Using Software
## Hugo
This section details how to create and modify pages for this website. The MyPaint
website is created using [Hugo][hugo], a [static site generator][ssg]. Pages are
written in [Markdown][md] (here's a [guide][md-guide]).

[hugo]: https://gohugo.io/
[ssg]: https://en.wikipedia.org/wiki/Static_site_generator
[md]: https://en.wikipedia.org/wiki/Markdown
[md-guide]: https://www.markdownguide.org/

Quick start (Desktop):
- At the left side of this page, there's an aside menu with a *"Page Information"* heading.
- Under the *Page Information* heading, there is a link to the source markdown file
for this page. Click it.
- Start getting your bearings by comparing what you see on the source file to what
you see on this page.

Conventions to follow when creating or modifying pages:
- Break lines before the word that *starts* after the 80th column
- Pages have [summaries][hugo-summary] generated from page content or front matter.
They may be created:
    1. Automatically at the 70th word
    2. At the position of the \<!\-\-more\-\-\> tag in the content.
    3. In front matter, using the ``summary`` key.
    - **Try to avoid the first case here and instead use case 2 or 3.**

### Other
- {{< id "main-image" >}}**Main page image:**{{< /id >}} [Page bundles][hugo-bundle] may include a file named ``index.jpg`` or ``index.png``,
preferrably accompanied with the [imgAlt front matter]({{< relref "#imgalt" >}}).
Such image files will:
    - Render the image behind the page title.
    - Add meta image tags (for e.g. [OpenGraph][opengraph])

[hugo-bundle]: https://gohugo.io/content-management/page-bundles/
[opengraph]: https://ogp.me/

### Front Matter
Front matter is used to store a page's metadata. Refer to [this page](https://gohugo.io/content-management/front-matter/).
to learn how to use front matter. This site's front matter is written in [TOML](https://toml.io/en/).

|Name|Value|Optional?|Description|
|:---|:----|:--------|:----------|
|title|String|No|Describe a title for the page|
|author|String|Yes|Describe an author for the page|
|date|[RFC 3339][rfc-3339]|Yes|Describe a creation/first published timestamp for the page|
|[summary][hugo-summary]|String|Yes|Define a summary instead of using page content|
|draft|Boolean|Yes|Describe the page as a [draft][hugo-draft]. These aren't published in the production environment|
|{{< id "imgalt" >}}imgAlt{{< /id >}}|String|Yes|Describe the alt attribute for the page's [main image]({{< relref "#main-image" >}})|
|sectionNavURL|Path|Yes|Enable the site navigation widget in aside at the path described|
|showInfo|Boolean|Yes|Display page git info|

[rfc-3339]: https://datatracker.ietf.org/doc/html/rfc3339
[hugo-draft]: https://gohugo.io/methods/page/draft/
[hugo-summary]: https://gohugo.io/content-management/summaries/

#### List Pages
|Name|Value|Optional?|Description|
|:---|:----|:--------|:----------|
|hideSummary|Boolean|Yes|Don't render the summary in the page body|
|hideList|Boolean|Yes|Don't render the list of pages|
|listByTitle|Boolean|Yes|Render list items alphabetically instead of by date|
|reverseList|Boolean|Yes|Reverse the order of list items|

### Shortcodes
Shortcodes extend markdown with custom HTML templates. Refer to [this page](https://gohugo.io/content-management/shortcodes/)
to learn how to use shortcodes.

#### Useful Hugo Builtin Shortcodes
|Shortcode|Type|Parameters|Description|
|:--------|:---|:---------|:----------|
|[``ref``][hugo-ref]|Inline|``0``: Path|Create an [anchor][html-a] to the specified page|
|[``relref``][hugo-relref]|Inline|``0``: Path|Create an [anchor][html-a] to the specified page *relative to the current directory*|

[hugo-ref]: https://gohugo.io/methods/shortcode/ref/
[hugo-relref]: https://gohugo.io/methods/shortcode/relref/

#### Custom Shortcodes
|Shortcode|Type|Parameters|Description|
|:--------|:---|:---------|:----------|
|``button``|Inline|``content``: string, [``href``][html-a-href]: path, [``src``][html-img-src]|Add a styled [anchor][html-a] labelled ``content`` with an image (optional)|
|``colour``|Content|``0``: oneof (red, yellow)|Change the [colour][css-color] of the contained text|
|``flex``|Content|[``direction``][css-flex-direction]: oneof (column, row), [``grow``][css-flex-grow]: boolean|Enclose the contained content in a [flexbox][css-flexbox]|
|``grid``|Inline|[``rows``][css-rows], [``columns``][css-columns], [``align``][css-align]|Enclose the contained content in a [grid][css-grid]|
|``id``|Content|``0``: string|Enclose the contained content in a [``span``][html-span] tag with [``id="0"``][html-attr-id]|
|``img``|Inline|[``alt``][html-img-alt]: string, [``src``][html-img-src]: path, ``caption``: string, [``float``][css-float], [``width``][css-max-width] |Insert an [image][html-img]|
|``md``|Content|None|Renders markdown in contained content (for [shortcodes without markdown][hugo-shortcode-nomd])|

[css-align]: https://developer.mozilla.org/en-US/docs/Web/CSS/align-items
[css-color]: https://developer.mozilla.org/en-US/docs/Web/CSS/color
[css-columns]: https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns
[css-flexbox]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout
[css-flex-direction]: https://developer.mozilla.org/en-US/docs/Web/CSS/flex-direction
[css-flex-grow]: https://developer.mozilla.org/en-US/docs/Web/CSS/flex-grow
[css-grid]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
[css-float]: https://developer.mozilla.org/en-US/docs/Web/CSS/float
[css-max-width]: https://developer.mozilla.org/en-US/docs/Web/CSS/max-width
[css-rows]: https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-rows
[hugo-shortcode-nomd]: https://gohugo.io/content-management/shortcodes/#shortcodes-without-markdown
[hugo-params]: https://gohugo.io/variables/site/#methods:site:param
[html-attr-id]: https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id
[html-a]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a
[html-a-href]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#href
[html-img]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img
[html-img-alt]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#alt
[html-img-src]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#src
[html-span]: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span

## Python
### Docstrings
We seem to be settling on [Sphinx](http://sphinx-doc.org/)'s [autodoc syntax](http://sphinx-doc.org/ext/autodoc.html#module-sphinx.ext.autodoc) for writing docstrings. Where it doesn't contradict, please follow [PEP 257](http://www.python.org/dev/peps/pep-0257/) too.

Python code should always have docstrings describing _what_ a public function or class does. We would like to use Sphinx's `autodoc` to generate API documentation one day, but conventions have not yet been settled for it. For now, please document parameters using Sphinx-style [info field lists](http://www.sphinx-doc.org/en/stable/domains.html#info-field-lists), and try not to use too much additional ReStructuredText markup.

```python
class Example (_ExampleBase):
    """Demonstrative example class."""

    def add_two(self, n1, n2):
        """Adds two numbers, or other objects.

        :param object n1: The first object to addify.
        :param object n2: The second object to addulate.
        :returns: The summified results of the two arguments.

        Any kind of object can be added provided it's supported
        by the builtin "+" operator. You might as well use that.

        """
        return n1 + n2
```

When it's not obvious what a bit of code is doing, add comments to explain _why_ you are doing something.
