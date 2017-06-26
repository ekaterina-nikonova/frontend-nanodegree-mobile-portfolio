## Improvements and fixes

### All files

* Compressed all images with [Optimizilla](http://optimizilla.com/).
* Added ``media`` query in the ``print.css`` link.
* Added ``async`` keyword in ``script`` tags.
* Moved scripts to the bottom of the page.
* Added async scripts for creating ``link``'s to CSS files AFTER the ``body`` loads. It makes little sense to inline CSS since the same ``style.css`` file is used across multiple pages.

### Index.html
* Replaced pizzeria thumbnail with a smaller image.
* Removed unused ``700`` style from **Google Fonts** link.

Screenshots of Dev Tools diagrams and Page Speed Insights reports before and after the optimization can be found in the ``report`` folder.

### Pizza.html
* Resized the pizzeria image (it's never larger than 720px).

### 60-fps pizzeria (main.js)
* Removed ``determineDx()`` function, used a simpler size calculations inside the ``changePizzaSizes()`` based on the ``sizeSwitcher()`` return values. Eliminated requests in the loop that caused forced layout reflow. See lines 425 - 452.

* The number of generated background pizzas now depends on the viewport size. See lines 527 - 532.

* In the ``updatePositions()``, the variable ``scrollPosition`` is now declared outside the loop and no longer causes layout reflow. See line 505.
