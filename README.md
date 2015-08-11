### Link to deployed Portfolio

<a href="http://lab.onclud.com/udportfolio">Portfolio</a>

### Optimizations in index.html

Page Speed Insights gives a score of 99 in both desktop and mobile version. To achieve that these are the optimizations applied to the project:

* Resize and compress images to decrease the size of them without quality lose.
* Add media query 'print' to print.css to unblock critical rendering path.
* Minify css and js resources.
* Inline CSS (not a good practice but as it's ok on that simple site).
* Add async attribute for blocking scripts to analytics.js and perfmatters.js
* Change the source of analytics script to <a href="http://sourceforge.net/projects/schedule-analytics/">Schedule-Analytics Script</a>. The reason of that is to solve the 'Leverage browser caching' issue related to analytics.js script.
* Add the next code to .htaccess to Leverage Browser Caching.

### Improvements in main.js

After the improvements explained above, the pizza.html project has a better performance under 60FPS when the user scrolling and a time under 5ms when resizing pizzas.

* Got rid of some lines from the loop at the end of changePizzaSizes (line#473) because they were repeating the work. To achieve a better performance the selection of 'randomPizzaContainer' has been moved out of the loop.
* Now the function determineDx is not necessary because the width calculation in changePizzaSizes is now simpler.
* Move out the loop of the function updatePositions (line #493) the code that produce Forced Synchronous Layout. This way we prevent the DOM explicitily touched in every interation.
* In DOCContentLoaded event (line#520) the 'movingPizzas1' element selection is move out of the loop, the number of cycles are reduced to 48 and the elem variable is created outside the loop as well.

### Improvements in views/css/style.css

* In the .mover selector (line#40) has been added the backface-visibility property with the 'hidden' value to offer a better support in no so powerful devices.