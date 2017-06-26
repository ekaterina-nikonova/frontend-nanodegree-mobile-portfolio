## Improvements and fixes

### All files

1. Compressed all images with [Optimizilla](http://optimizilla.com/).
2. Added ``media`` query in the ``print.css`` link.
3. Added ``async`` keyword in ``script`` tags.
4. Moved scripts to the bottom of the page.
5. Added async scripts for creating ``link``'s to CSS files AFTER the ``body`` loads. It makes little sense to inline CSS since the same ``style.css`` file is used across multiple pages.

### Index.html
1. Replaced pizzeria thumbnail with a smaller image.
2. Removed unused ``700`` style from **Google Fonts** link.

### Pizza.html
1. Resized the pizzeria image (it's never larger than 720px).

### 60-fps pizzeria (main.js)
* Removed ``determineDx()`` function, used a simpler size calculations inside the ``changePizzaSizes()`` based on the ``sizeSwitcher()`` return values. Eliminated requests in the loop that caused forced layout reflow. See lines 425 - 452.

* The number of generated background pizzas now depends on the viewport size. See lines 527 - 532.

* In the ``updatePositions()``, the variable ``scrollPosition`` is now declared outside the loop and no longer causes layout reflow. See line 505.
