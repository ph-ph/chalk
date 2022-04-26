# Chalk
Chalk is a port of [Nielsen Ramon's Jekyll theme](https://github.com/nielsenramon/chalk) to [Hugo](https://gohugo.io) .

Most of the theme features have been preserved, except for optional tag-based navigation.

## Contents

- [Installation](#installation)
- [Options and features](#options-and-features)
- [Support](#support)
- [Author](#author)
- [Ported by](#ported-by)
- [License](#license)

## Installation

To install Chalk as your default theme, first install this repository in the `themes/` directory:

    $ git submodule add https://github.com/ph-ph/chalk.git themes/chalk

Second, specify `chalk` as your default theme in the `config.toml` file. Just add the line

    theme = "chalk"

at the top of the file.

## Options and features
Theme-specific configuration lives under `params.chalk` section of your config.toml file:

```toml
[params.chalk]
  # chalk theme parameters
  about_enabled = true # Change to true if you wish to show an icon in the navigation that redirects to the about page
  scrollappear_enabled = true
  theme_toggle = true
  rss_enabled = true
  blog_theme = 'light' # Doesn't matter if theme_toggle = true
  local_fonts = false
```

Available settings:

* `about_enabled` - set to true if you wish to show an icon in the navigation that redirects to the about page.
* `discus_identifier` - set to your Disqus identifier (NOTE: I may remove this in the future in favor of standard Hugo Disqus configuration).
* `ga_analytics` - set to your Google Analytics Tracking Id (NOTE: I may remove this in the future in favor of standard Hugo Google Analytics configuration).
* `local_fonts` - set to true if you want to use fonts provided in this repository.
* `rss_enabled` - set to true if you want a link to RSS feed displayed in the nav header.
* `scrollappear_enabled` - set to true if you want page elements slowly fade in as you scroll the page.
* `blog_theme` - can be either 'light' or 'dark'.
* `theme_toggle` - set to true if you want a dark/light switch in the nav header. If set to true, default scheme is always light.

You can add your social accounts in `params.social` section of your config.toml:
```toml
[params.social]
  twitter='example'
  github='example'
```
See [config file](data/social/sites.toml) for a list of supported sites (there's plenty).

#### SCSS

You can change colors, fonts, sizes in the `assets/stylesheets/_variables.scss` file.
For each specific theme (light or dark) you can change the variables in `assets/stylesheets/dark.scss` and `assets/stylesheets/light.scss`.

```scss
// =============================================================================
// Variables
// =============================================================================

// Typography
// =============================================================================

$sans-serif: "Lato", Helvetica, Arial, sans-serif;
$serif: "Cormorant Garamond", Courier, serif;
$base-font-family: $sans-serif;
$base-font-weight: 400;
$base-font-weight-bold: 700;

// Colors
// =============================================================================

// Brand colors

$brand-success: #1fbf92;
$brand-danger: #e74b3c;
$brand-primary: #3449ed;
$brand-warning: #f1c90b;

// Sizes
// =============================================================================

// Grid

$columns: 12;
$max-width: 650px;
$gutter: 20px;
$one-column: 100% / $columns;
$negative-gutter: 0 - $gutter;

// Font sizes

$base-font-size: 16px;
$article-list-font-size: 15px;
$base-line-height: 1.8;

// Box sizes

$base-border-radius: 4px;

// Effects
// =============================================================================

$base-transition-speed: .2s;
```

#### Fonts

Chalk uses Google Fonts by default. You can change the font in `assets/javascripts/webfonts.js` and in `404.html`.

```javascript
WebFont.load({
  google: {
    families: ['Cormorant Garamond:700', 'Lato:300,400,700']
  }
});
```

Don't forget that Chalk also supports local fonts if enabled in `config.toml`!

#### Zoomable images
There's an `image` shortcode that allows you to insert Medium-style images that can be zoomed-in:
```
{{< image path="images/image.jpg" path_detail="images/image@2x.jpg" alt="Image alt text" >}}
```

* `path` - relative image path in your `assets` folder (NOTE: I _think_ it has to be in `assets/images` for Hugo to serve it correctly, but I might be wrong).
* `path_detail` - relative path of higher-definition image in `assets` folder. You can omit this, in which case the original image will be used.
* `alt` - Image alt text.

## Support
I don't plan to actively support and develop this theme, and will not try to port all the future changes in the original theme.

That said, message me or open an issue if something is broken or there's an easy way to make the theme better. PRs are very much welcome.

## Author
**Nielsen Ramon**
- <https://github.com/nielsenramon>

## Ported By
**Dzmitry Kishylau**
- <https://github.com/ph-ph>

## License

Open sourced under the [MIT license](LICENSE).
