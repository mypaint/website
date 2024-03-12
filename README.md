# MyPaint Website
This repository holds the page data for [MyPaint.org][mypaint]. It uses the [Hugo][hugo]
static site generator and [Dart Sass][sass].

The official MyPaint website repository is hosted on [GitHub][github]. The theme
is hosted [here][website-theme].

[mypaint]: https://mypaint.org
[hugo]: https://gohugo.io
[sass]: https://sass-lang.com/dart-sass
[github]: https://github.com/mypaint/website
[website-theme]: https://github.com/mypaint/website-theme

# Contributing
To build this repository:
1. Install [hugo-extended][hugo-release], [dart sass][sass-release], and [git-lfs](https://git-lfs.com/)
2. Clone this repo
3. Run ``git submodule update --init``
4. Run ``hugo`` or ``hugo server``

[hugo-release]: https://github.com/gohugoio/hugo/releases
[sass-release]: https://github.com/sass/dart-sass/releases

## Update submodules
When [website-theme][website-theme] or other submodules are updated, use
``git submodule update --recursive --remote`` to reflect the changes in
your development environment.

## Adding content
Page content is stored in the [pages](/pages/) directory. Pages are written in
[markdown][hugo-learn-md] and [extended][hugo-content] by Hugo.

To add a new page to the website, type ``hugo new content pages/path/to/filename.md``.

[hugo-learn-md]: https://gohugo.io/content-management/formats/#learn-markdown
[hugo-content]: https://gohugo.io/content-management/

### Writing developer documentation
Making changes to MyPaint? Follow [this guide][developer-docs] to get started
writing documentation.

# License
All text in the website is licensed under [CC-BY-SA 4.0][cc-by-sa].
Additional terms may apply.

[developer-docs]: https://horizon.mypaint.app/en/docs/contributing/documentation
[cc-by-sa]: https://creativecommons.org/licenses/by-sa/4.0/
