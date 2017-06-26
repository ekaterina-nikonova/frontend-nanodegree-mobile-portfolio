## Testing

This is the Website Optimization Project for the Udacity Front-End Web Development Nanodegree. The live version of this site is hosted [here](https://ekaterina-nikonova.github.io/frontend-nanodegree-mobile-portfolio/). To test the ``index.html`` file at Page Speed Insights, just click [this link](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fekaterina-nikonova.github.io%2Ffrontend-nanodegree-mobile-portfolio).

If screenshots of my Dev Tools diagrams and Page Speed Insights reports before and after the optimization are of any interest, they can be found in the ``report`` folder.

My comments across all files begin with ``EN:``.

## Improvements and fixes

### All files

* Compressed all images with [Optimizilla](http://optimizilla.com/).
* Added ``media`` query in the ``print.css`` link.
* Added ``async`` keyword in ``script`` tags.
* Moved scripts to the bottom of the page.
* Added scripts for creating ``link``'s to CSS files AFTER the ``body`` loads. It makes little sense to inline CSS since the same ``style.css`` file is used across multiple pages.

### Index.html
* Replaced pizzeria thumbnail with a smaller image.
* Removed unused ``700`` style from **Google Fonts** link.


### Pizza.html
* Resized the pizzeria image (it's never larger than 720px).

### 60-fps pizzeria (main.js)
* Removed ``determineDx()`` function, used a simpler size calculations inside the ``changePizzaSizes()`` based on the ``sizeSwitcher()`` return values. Eliminated requests in the loop that caused forced layout reflow. See lines 425 - 452.

* The number of generated background pizzas now depends on the viewport size. See lines 527 - 532.

* In the ``updatePositions()``, the variable ``scrollPosition`` is now declared outside the loop and no longer causes layout reflow. See line 505.
