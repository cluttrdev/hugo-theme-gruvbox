# hugo-gruvbox

A retro-looking [Hugo](https://gohugo.io/) theme inspired by [gruvbox](https://github.com/morhetz/gruvbox).
The pastel colors are high contrast, easily distinguishable, pleasing to the
eye, and feature light and dark color palettes.

## DISCLAIMER: Project Status

This theme is still under heavy development and not production ready.
[Check out the issues](https://github.com/schnerring/hugo-gruvbox/issues) to see
what features are missing. As soon as the core features are implemented, I will
publish it to the [Hugo showcase](https://themes.gohugo.io/) and release
version v0.1.0.

## Features

- Code highlighting with [Prism](https://prismjs.com/)
- [Tabler Icons](https://tabler-icons.io/) for generic icons
- [Simple Icons](https://simpleicons.org/) for social icons
- All third-party dependencies are managed with [npm](https://www.npmjs.com/)
  to make updating a breeze and reduce code clutter
- Dark mode that also changes Prism themes

Big thanks to the creators of [Hugo](https://gohugo.io/) and the software
mentioned above. Also, thanks to everyone participating in open-source. I
couldn't have created this theme without you. ❤️

## Installation

Run `npm ci` before running `hugo`.

## Configuration

### Colors

Two options are available to configure the theme's colors:

- `defaultTheme`: `dark` or `light` (defaults to `light`)  
  Default theme color for when a user visits the site for the first time.
- `defaultColor`: `gray`, `red`, `green`, `yellow`, `blue`, `purple`, `aqua`, or
  `orange` (defaults to `blue`)  
   Default color for things such as links, headings etc.

### Prism

The theme allows customization of Prism via `config.toml` parameters:

```toml
[params]
  [params.prism]
    languages = [
      "markup",
      "css",
      "clike",
      "javascript"
    ]
    plugins = [
      "normalize-whitespace",
      "toolbar",
      "copy-to-clipboard"
    ]
```

In my opinion, this is the coolest feature of the theme. Other Hugo themes
usually include a pre-configured version of Prism, which complicates updates and
change tracking, and clutters the theme's code base with third-party JavaScript.

The Prism theme is not configurable because of the integration with the dark
mode functionality. Toggling between color modes swaps the Prism theme between
[`gruvbox-dark`](https://github.com/PrismJS/prism-themes/blob/master/themes/prism-gruvbox-dark.css)
and [`gruvbox-light`](https://github.com/PrismJS/prism-themes/blob/master/themes/prism-gruvbox-light.css)
from [github.com/PrismJS/prism-themes](https://github.com/PrismJS/prism-themes).

#### Explore Prism Features

After running `npm install`, explore Prism features like this:

```shell
# Languages
ls node_modules/prismjs/components

# Plugins
ls node_modules/prismjs/plugins
```

## Extensibility

You can extend the theme by overriding the following partials in the `layouts/partials`
directory which by default are empty placeholder files:

- [`head/head_start.html`](./layouts/partials/head_start.html)  
  Custom HTML at the start of `<head>`
- [`head/head_end.html`](./layouts/partials/head_end.html)  
  Custom HTML at the end of `<head>`
- [`footer_end.html`](./layouts/partials/footer_end.html)  
  Custom HTML at the end of `<body>`
- [`comments.html`](./layouts/partials/comments.html)  
  Comments at the end of posts
