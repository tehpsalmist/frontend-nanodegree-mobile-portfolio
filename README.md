## Website Performance Optimization portfolio project

The purpose of this project was to optimize the critical rendering path and make this page and its subpages render as quickly as possible by applying the techniques taught in the [Critical Rendering Path course](https://www.udacity.com/course/ud884) by Udacity.

Check out the [original repository](https://github.com/udacity/frontend-nanodegree-mobile-portfolio) to compare the code.

### Part 0: Check it out

To see the optimized pages in action, [download](https://github.com/tehpsalmist/frontend-nanodegree-mobile-portfolio/archive/master.zip) or clone the directory and open `index.html` in your favorite browser, or [view the page live](https://tehpsalmist.github.io/frontend-nanodegree-mobile-portfolio/) (hosted on GitHub Pages).

`git clone https://github.com/tehpsalmist/frontend-nanodegree-mobile-portfolio.git`

### Part 1: Optimize PageSpeed Insights score for [index.html](https://tehpsalmist.github.io/frontend-nanodegree-mobile-portfolio/)

The Github Pages rendering of the home page scored 92/100 on mobile and 95/100 on desktop with [Google's Pagespeed Insights](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Ftehpsalmist.github.io%2Ffrontend-nanodegree-mobile-portfolio%2F&tab=mobile).

I achieved this by
1. Optimizing/compressing all images on [resizeimage.net](http://resizeimage.net)
1. Inlining a minified version of the styles in the `<head>` using [CSS Minifier](https://cssminifier.com/)
1. Adding `async` to the google analytics script and `perfmatters.js`
1. Refactoring the CSS/HTML styles to utilize classes and generic tag styles (eliminated many descendent selectors)
1. Dispensed of the unnecessary webfonts
1. Added `media="print"` to `print.css` so it wouldn't be included unnecessarily

### Part 2: Optimize Frames per Second in [pizza.html](https://tehpsalmist.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html)

The animations on this page (resizing pizzas and "on-scrolling" pizzas in the background) run at a buttery 60 frames per second, thanks to these optimizations in the JavaScript and CSS:

1. Optimized the pizza images by transforming them into [base64 data](https://www.base64-image.de/) (holy huge performance boost batman!)
2. 