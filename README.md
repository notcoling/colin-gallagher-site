# Hyde-Like

This project is a refresh of the [Hyde](https://github.com/poole/hyde) theme for [Jekyll](https://jekyllrb.com/). Hyde is a brazen two-column Jekyll theme that pairs a prominent sidebar with uncomplicated content.

This version has been made in order to use the theme with the latest version of Jekyll.

There is another theme very similar to this, [Hydeout](https://github.com/fongandrew/hydeout), that seeks to accomplish the same thing. However it includes some additional improvements to the layout, Discuss comments, and Google Analytics.

The goal of this project was to add as few improvements as possible in order to keep the original look and feel of the Hyde theme.

## Contents

- [Installation](#installation)
- [Usage](#usage)
- [Options](#options)
  - [Sidebar menu](#sidebar-menu)
  - [Sticky sidebar content](#sticky-sidebar-content)
  - [Themes](#themes)
  - [Reverse layout](#reverse-layout)
- [Improvements](#improvements)
- [Development](#development)
- [Authors](#authors)
- [License](#license)

## Installation
Just download and start the Jekyll server!

```
jekyll serve
# alternatively you can also use:
# bundle exec jekyll serve
```

If you need more detailed instructions for installing Ruby or Jekyll you can find it in the link below.

- [Jekyll Installation (with Ruby installation instructions by platform)](https://jekyllrb.com/docs/installation/)

You can also get started with this project on Netlify by clicking the button below:

<!-- Markdown snippet -->
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/notcoling/hyde-like)

## Usage

When you have your site up and running locally, you can modify the styles found in the `public/css` folder, add posts to `_posts`, and modify `_config.yml` to reflect your social media and site information.

## Options
Hyde-Like preserves the options included in the original Hyde theme. There are some customizable options, typically applied via classes on the `<body>` element.

### Sidebar menu

Create a list of nav links in the sidebar by assigning each Jekyll page the correct layout in the page's front-matter.

```
---
layout: page
title: About
---
```

Why require a specific layout? Jekyll will return all pages, including the atom.xml, and with an alphabetical sort order. To ensure the first link is Home, we exclude the index.html page from this list by specifying the page layout.

Sticky sidebar content
By default Hyde ships with a sidebar that affixes it's content to the bottom of the sidebar. You can optionally disable this by removing the .sidebar-sticky class from the sidebar's .container. Sidebar content will then normally flow from top to bottom.

```html
<!-- Default sidebar -->
<div class="sidebar">
  <div class="container sidebar-sticky">
    ...
  </div>
</div>

<!-- Modified sidebar -->
<div class="sidebar">
  <div class="container">
    ...
  </div>
</div>
```

### Themes
Hyde ships with eight optional themes based on the base16 color scheme. Apply a theme to change the color scheme (mostly applies to sidebar and links).

There are eight themes available at this time.

Hyde theme classes:
- .theme-base-08 (Red)
- .theme-base-0c (Green)
- .theme-base-09 (Orange)
- .theme-base-0d (Blue)
- .theme-base-0a (Yellow)
- .theme-base-0e (Purple)
- .theme-base-0b (Green)
- .theme-base-0f (Brown)

To use a theme, add anyone of the available theme classes to the `<body>` element in the default.html layout, like so:

```html
<body class="theme-base-08">
  ...
</body>
```

To create your own theme, look to the Themes section of included CSS file. Copy any existing theme (they're only a few lines of CSS), rename it, and change the provided colors.

### Reverse layout

Hyde's page orientation can be reversed with a single class.

```html
<body class="layout-reverse">
  ...
</body>
```

## Improvements

One improvement made to Hyde in this Hyde-Like Jekyll site is the inclusion of Font-Awesome icons. 

In order to use the icons, just include one of the items listed on [Font Awesome's Icon page](https://fontawesome.com/icons) in any HTML included in this theme.

```html
<span>
  <i class="fab fa-github"></i>
</span>
```

Font Awesome is included locally in the `public/css` folder. If you don't wish to use it, just delete the directory and remove the stylesheet from `default.html`.

## Development
Hyde-Like has only one branch in for active development.
- `master` for development. All pull requests should be submitted against master.
- `netlify` for the hosted demo version of this theme.

## Authors
Colin Gallagher - Hyde-Like author
- https://github.com/notcoling
- https://twitter.com/notcolinn

Mark Otto - Original Hyde Jekyll theme author
- https://github.com/mdo
- https://twitter.com/mdo


## License
Open sourced under the MIT license. ⚖️ ❤️