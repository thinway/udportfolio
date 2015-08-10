### Link to deployed Portfolio

<a href="http://lab.onclud.com/udportfolio">Portfolio</a>

### Some of the Optimizations done

Page Speed Insights gives a score of 99 in both desktop and mobile version. To achieve that these are the optimizations applied to the project:

* Resize and compress images to decrease the size of them without quality lose.
* Add media query 'print' to print.css to unblock critical rendering path.
* Minify css and js resources.
* Inline CSS (not a good practice but as it's ok on that simple site).
* Add async attribute for blocking scripts to analytics.js and perfmatters.js
* Change the source of analytics script to <a href="http://sourceforge.net/projects/schedule-analytics/">Schedule-Analytics Script</a>. The reason of that is to solve the 'Leverage browser caching' issue related to analytics.js script.
* Add the next code to .htaccess to Leverage Browser Caching

	```<IfModule mod_expires.c>
ExpiresActive On

ExpiresByType image/jpg "access 1 year"
ExpiresByType image/jpeg "access 1 year"
ExpiresByType image/gif "access 1 year"
ExpiresByType image/png "access plus 10 minutes"
ExpiresByType text/css "access 1 month"
ExpiresByType text/js "access 2 hour"
ExpiresByType text/html "access 1 month"
ExpiresByType application/pdf "access 1 month"
ExpiresByType text/x-javascript "access 1 month"
ExpiresByType application/x-shockwave-flash "access 1 month"
ExpiresByType image/x-icon "access 1 year"
ExpiresDefault "access plus 1 month"
</IfModule>
	```
### Computation Efficiency for pizza.html

To speed up the pizzeria, I got rid of some code that was too heavy for the process. The time to generate the web is about ~16ms. After that, the time is about 0.1ms to generate. When I use the changing pize size slider the time elapsed is about ~0.35ms.