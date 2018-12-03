## Gradient - yet another hexo theme.
![](https://i.imgur.com/mgUL53h.jpg)

[Check out the demo](https://hackable.mk).

## Features
- Responsive
- Featured image
- Charts
- Twitter widget.

## External libraries used
- [Bootstrap 4 with Popper.js, and jQuery](https://getbootstrap.com/)
- [Font awesome](https://fontawesome.com/)
- [Chart.js](https://www.chartjs.org/)

## Installation

Install the theme by using:

`$ git clone https://github.com/RandomAdversary/Gradient.git themes/gradient`

Then update your blog's main _config.yml to set the theme to gradient.

## Configuration
The configuration is done in `themes/gradient/_config.yml`
### Menu
The object key is the label and the value is the path.
```
menu:
  HOME: /
  ARCHIVES: /archives
  '#RANDOM': /categories/random/
  CONTACT: /contact/
```

### Footer icons
The class value comes from font awesome. Example: if the html code for the icon is `<i class="fab fa-adversal"></i>` the value for class will be `fab fa-adversal`.
```
footer_icons:
  'Hexo.io':
    url: 'https://hexo.io/'
    class: 'fas fa-home'
  '@hexojs':
    url: 'https://twitter.com/hexojs'
    class: 'fab fa-twitter'
  'Report issue':
    url: 'https://github.com/RandomAdversary/Gradient/issues'
    class: 'fas fa-bug'
```

### Featured image
If the post doesn't contain the featured_image attribute, then the default image is used.

`featured_image: ./img/default.jpg`

### Sidebar
The sidebar contains 2 things, the TL;DR widget, which displays text and embedded twitter widget.
```
sidebar:
  twitter:
    username: 'hexojs'
    height: 800
  tldr: 'Gradient is clean and modern hexo theme.'
```

## Changelog
1.0
- Initial release.

1.1 
- Added charts.js support.

1.2
- New menu hover design. 
- Added sidebar with tl;dr (about) widget and twitter timeline.
