## The R Project Blog

### Overview

This is the source repository for [The R Project Blog](https://blog.R-project.org/)
where members of the R Core Team and the R Foundation, along with other contributors,
share news, insights, and plans related to the R core implementation and other
related topics.

- **Source repository:** <https://github.com/r-devel/blog.r-project.org>
- **Rendered version:** <https://contributor.r-project.org/blog.r-project.org/> _(for inspection, see below)_
- **Official site:** <https://blog.R-project.org/>
- **Tools:** [Quarto](https://quarto.org/) and [R](https://www.R-project.org/)


### Contributing

The blog is hosted by the R Core Team and the R Foundation and coordinated by
their social media team, currently:
[Dirk Eddelbuettel](https://github.com/eddelbuettel),
[Heather Turner](https://github.com/hturner),
[Martyn Plummer](https://github.com/martynplummer),
[Achim Zeileis](https://github.com/zeileis).

Members of the R Core Team and the R Foundation can send their contributions
either via e-mail to `social-media@R-project.org` or make a pull request in
this repository. Other contributors typically collaborate with a member of the
R Core Team or R Foundation when preparing their blog posts.

A blog post is typically a single R/Markdown (.Rmd) file with a YAML header
containing a `title` (in title case), `author` (comma-separated if needed),
`categories` (typically based on the list below), and a short `description`.
See previous posts for examples. Ideally, an `image` for the listing on the
landing page is also included.


### Categories

Every blog post should provide a couple of categories which readers can then
also use for navigation through the blog. In order to facilitate this, standard
categories like the ones below should be used if possible.

- **BLAS/LAPACK** - linear algebra libraries
- **C/C++** - C and C++ code issues, PROTECT/UNPROTECT, interoperability
- **classes/methods** - S3, S4, S7, OOP design, method dispatch
- **community** - contributions, translations, bug reports, mentoring, volunteering
- **CRAN** - CRAN package checking/compatibility
- **documentation** - help systems, vignettes, Sweave, educational materials
- **encoding** - character encoding, UTF-8, iconv, regex with encoding
- **Fortran** - Fortran compiler issues, LAPACK interoperability
- **graphics** - graphics engine, colors, visualization, patterns, gradients
- **internals** - internal R implementation, memory management, architecture
- **language** - parsing, language features, conditions, syntax
- **macOS** - macOS-specific implementation details
- **numerical** - numerical accuracy, math libraries, precision
- **packages** - package installation, management, CRAN, binary packages
- **performance** - speedups, optimizations, efficiency improvements
- **platform support** - hardware platforms, architectures, cross-platform work
- **QEMU** - platform emulation tool
- **R Core** - R Core Team work, major initiatives, architectural changes
- **R Foundation** - Foundation organization, governance, prizes, funding
- **security** - security issues, vulnerabilities, CVEs
- **Sweave** - literate programming framework
- **stats** - modeling and inference in base R
- **testing** - testing, debugging, QA, CRAN checks, regression tests
- **UCRT** - Windows Universal C Runtime
- **UTF-8** - when UTF-8 encoding is the focus
- **windows** - Windows-specific features, UTF-8, Rterm, paths


### Publishing

To officially publish the rendered blog at <https://blog.R-project.org/> the
following steps are used:

1. Add a new subdirectory in `posts` and push it to the `main` branch,
   either directly or through a pull request.
2. Double-check that the rendered version of the post looks ok,
   either locally or in the GitHub pages (see below).
3. Push the rendered website into the `publish` branch, from where it
   will be picked up automatically and deployed to the official URL
   above (approximately once per hour).

**Step 1:** This is done "as usual" in Git/GitHub.

**Step 2:** To render the website locally use

```
quarto render
```

and then inspect `_site/index.html` by opening it in the browser.

Additionally, the rendering is done upon any push to the `main` branch
by a GitHub Action running the
[quarto.yml](https://github.com/r-devel/blog.r-project.org/blob/main/.github/workflows/quarto.yml)
workflow. The rendered site is then pushed to the `gh-pages` branch
and can be inspected at <https://contributor.r-project.org/blog.r-project.org/>.

**Step 3:** For deploying the rendered site to the official URL
it needs to be pushed to the `publish` branch. This can either be done
from the locally rendered version or merged from the `gh-pages` branch:

```
git checkout gh-pages
git pull
git switch publish
git merge gh-pages
git push
```
