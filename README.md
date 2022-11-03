# [Herman][herman] [a [SassDoc][sassdoc] theme]

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/oddbird/sassdoc-theme-herman/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/oddbird/sassdoc-theme-herman/tree/main)
[![AppVeyor](https://ci.appveyor.com/api/projects/status/w02fa9k998fywntl/branch/main?svg=true)](https://ci.appveyor.com/project/jgerigmeyer/sassdoc-theme-herman/branch/main)
[![Codecov](https://codecov.io/gh/oddbird/sassdoc-theme-herman/branch/main/graph/badge.svg?token=dy36BBNFFu)](https://codecov.io/gh/oddbird/sassdoc-theme-herman)

> **If it's not documented, it doesn't exist.**
> Documentation should become the default --
> an integrated part of the development process.
>
> <cite>---<a href="https://www.oddbird.net/authors/miriam/">Miriam Suzanne</a></cite>

At [OddBird][oddbird],
we wanted better tools for documenting
the entire front end of a project --
from brand guidelines to UX patterns and code APIs:

- Documenting the intersection of languages and styles
- Written directly in the code,
  and integrated with code architecture
- Automated for a document that grows and changes
  along with the life of your project

Herman is built as an extension to [SassDoc][sassdoc],
and supports all their core functionality
with additional support for
[font specimens][font-docs], [color palettes][color-preview],
[sizes and ratios][size-preview], [SVG icons][icon-docs],
[compiled languages][example-docs], Nunjucks/Jinja macros, HTML previews,
and more.

[font-docs]: https://www.oddbird.net/herman/docs/demo_fonts.html
[color-preview]: https://www.oddbird.net/herman/docs/demo_colors.html
[size-preview]: https://www.oddbird.net/herman/docs/demo_sizes.html
[icon-docs]: https://www.oddbird.net/herman/docs/demo_icons.html
[example-docs]: https://www.oddbird.net/herman/docs/demo_examples.html

## Getting Started

```bash
npm install sassdoc sassdoc-theme-herman
```

Note: Dart Sass (`sass`)
is required to use Herman
to display samples of Sass/Scss code.
If it's not already installed in your project,
install it along with Herman:

```bash
npm install sass
```

See the [SassDoc documentation](http://sassdoc.com/getting-started/)
to run SassDoc via various build tools.
Specify `herman` as the theme
in your SassDoc options:

```bash
sassdoc <src> --theme herman
```

### SassDoc Comments

Currently,
all SassDoc/Herman annotations are written as Sass comments
starting with `///` to differentiate documentation
from other developer comments (`//`).

```scss
// This comment will be ignored by Herman
/// This comment will be rendered in the documentation
```

Annotation comments can be free-floating,
or attached to a particular Sass/CSS object --
such as a variable, mixin, function, or selector block.
Note that while SassDoc allows annotation comments
to be separated from the documented code by newlines,
Herman considers documentation to be free-floating "prose" if
it is separated from documented code by one or more newlines.

```scss
/// this is a free-floating comment

/// this comment is attached to the following mixin code-block
@mixin sample-object { … }
```

### Herman Annotations

In addition to the core SassDoc annotations,
our [`@icons` annotation][icon-docs] allows you to
display SVG icons from a given folder,
and we extend the core [`@example` annotation][example-docs]
to display compiled Sass/Nunjucks output
and render sample components.
We also provide a [`@font` annotation][font-docs]
for displaying font-specimens,
and `@colors`, `@sizes`, and `@ratios` annotations
for displaying [color-palettes][color-preview],
[text and spacing sizes, and modular ratios][size-preview].

[herman]: https://www.oddbird.net/herman/
[oddbird]: https://www.oddbird.net/
[sassdoc]: http://sassdoc.com/

[See the full documentation for details »][docs]

[docs]: https://www.oddbird.net/herman/docs/configuration

## SassDoc Extras

Herman uses a number of SassDoc Extras:

- [Description](http://sassdoc.com/extra-tools/#description-description-descriptionpath)
- [Display](http://sassdoc.com/extra-tools/#display-toggle-display)
- [GroupName](http://sassdoc.com/extra-tools/#groups-aliases-groupname)
- [ShortcutIcon](http://sassdoc.com/extra-tools/#shortcut-icon-shortcuticon)
- [Sort](http://sassdoc.com/extra-tools/#sort-sort)
- [ResolveVariables](http://sassdoc.com/extra-tools/#resolved-variables-resolvevariables)
