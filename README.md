## SF Tri Workbench
Tools, assets, and documentation for working in SF Tri's online space.

### Getting Started
These are a few steps that you need perform only once.

#### git
The first thing you will need to do is [download and install git](http://git-scm.com/downloads) on your system. Then from a terminal, clone the sftriclub repository
```
git clone git@github.com:sftriclub/workbench.git
```
This will create a repository on your drive in a folder called `workbench`. The rest of the setup steps shoule be done from the top-level of this repository.

#### bundler
From within the top-level directory of the `workbench` repository
```
gem install bundler
```
then bring in the project's dependencies
```
bundler install
```

### Tools
These are a few tools here that will help you get your job done.

#### foreman
A simple tool to start your services (such as sass).

Usage:
```
foreman start [<service>]
```
This starts the services (or an optional specified service). See the `Procfile` in the repository and the [man page](http://ddollar.github.io/foreman/) for further explanation.

#### scss
We are using Sass to manage our css files. New scss files should be saved anywhere under `assets/stylesheets/` and need to end in `.scss`. They should then be added after the list of base scss files in `wildapricot.scss` which is setup as a manifest for all scss.
By running the Sass service with `foreman start`, changes to your scss files will automatically be detected and be compiled into `wildapricot.css`. Check [the documentation](http://sass-lang.com/guide) on the main sass website for an overview of the basics or for an exhaustive explanation see [this online documentation](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)

`wildapricot.scss` imports the following base files:

- `mixins.scss` - A place for all sass [mixin logic](http://sass-lang.com/guide#topic-6)
- `reset.scss` - A set of css rules to establish a browser-neutral, clean baseline from which to start styling. **Note:** Need to test whether this messes with Wild Apricots templates. Also, they may already provide a set of css reset stylings. ([html 5 doctor](http://html5doctor.com/html-5-reset-stylesheet/))
- `base.scss` - A place to keep our site-wide base styling.

Any new files you add should follow these base files.

#### scss-link
A tool to quickly verify the quality of your scss. Running this will scan all scss files in `assets/stylesheets/` and report on a variety of code quality rules called linters.

Usage:
```
scss-lint
```
Refer to the [online documentation](https://github.com/causes/scss-lint/blob/master/lib/scss_lint/linter/README.md) for more details about these rules.
Certain linters have been modified or disabled. See the `.scss-link.yml` file for details.

### Best Practice
- Keep scss organized into small, subject related files and add them to the `wildapricot.scss` manifest file below the three base files indicated above.
- Always run `scss-lint` before committing/pushing changes.

### Style Guide
:construction: This is setup as a template suggestion.

#### @mixins
- cool-function(px, ...)

#### $color-library
- `$sftc-green` - SF Tri's primary green color
- `$base-text` - Color for all basic text

#### css
- .button - styling for the button
 - .primary - default/highlighted button
 - .cancel - lowlight styling
