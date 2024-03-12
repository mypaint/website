# MyPaint Website
This repository holds the page data for [MyPaint.org][mypaint]. It uses the [Hugo][hugo]
static site generator and [Dart Sass][sass].

The official MyPaint website repository is hosted on [GitHub][github]. The theme
is hosted [here][website-theme].

[mypaint]: https://mypaint.org
[hugo]: https://gohugo.io
[sass]: https://sass-lang.com/dart-sass
[github]: https://github.com/mypaint/website
[github]: https://github.com/mypaint/website-theme

# Contributing
To build this repository:
1. Install hugo-extended, dart sass, and [git-lfs](https://git-lfs.com/)
2. Clone this repo
3. Run ``git submodule update --init``
4. Run ``hugo`` or ``hugo server``

## Adding content
Page content is stored in the [pages](/pages/) directory. Pages are written in
[markdown][hugo-learn-md] and [extended][hugo-content] by Hugo.

[hugo-learn-md]: https://gohugo.io/content-management/formats/#learn-markdown
[hugo-content]: https://gohugo.io/content-management/

### Writing developer documentation
Making changes to MyPaint? Follow [this guide][developer-docs] to get started
writing documentation.

# License
All text in the website is licensed under [CC-BY-SA 4.0][cc-by-sa].
Additional terms may apply.

[developer-docs]: https://mypaint.org/design/contributing/documentation
[cc-by-sa]: https://creativecommons.org/licenses/by-sa/4.0/
