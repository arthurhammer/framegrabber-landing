# Frame Grabber Landing Page

This site is hosted on GitHub pages, at https://arthurhammer.github.io/framegrabber-landing/.

## Run Locally

Besides [ruby](https://www.ruby-lang.org), make sure [bundler](https://bundler.io) is installed. Jekyll itself is installed as a project dependency.

**Install dependencies**:

    bundle install --path=vendor/bundle

**Run a local server**:

    bundle exec jekyll serve --livereload

**Build site**:

    bundle exec jekyll build

## Relative Links

The original repo has several issues with relative links. GitHub Pages without a custom domain runs on `user.github.io/repo/` while a local test server usually runs on `/`. Neither absolute nor unqualified relative links work for both cases at the same time.

Instead, use qualified relative links with `site.baseurl` (`site.baseurl` is typically empty on the local server and points to `repo` on GitHub Pages).

This can be done something like so:

    {{ site.app_icon | relative_url }}              # variables can be qualified with the relative filter
    {{ site.baseurl }}{% link _pages/privacy.md %}  # link tags must be qualified manually
    {{ site.baseurl }}/main.css                     # individual files also qualified manually

## Jekyll Version

Note when consulting the documentation, the Jekyll version on GitHub Pages (currently) is 3.9.0.