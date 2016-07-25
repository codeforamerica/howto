**This documentation is being deprecated!**
Please update your links to [here](https://wiki.codeforamerica.org)
Future changes will be made from [this github repository](https://github.com/codeforamerica/cfa-wiki)


Old Browsers
============

####TL;DR: 
* Use [html5boilerplate](https://html5boilerplate.com/) to start your project and avoid 80% of headaches.
* When in doubt, look up any compatibility questions on http://caniuse.com/

-----

Old browsers present challenges in a few different dimensions:
* HTML
* CSS
* JS
* Testing

Each of these topics are dealt with in turn below. A "Tools" section at the bottom summarizes the many external tool references made throughout this document.

The tools and methods documented here are targeted toward IE 8 and 9, and may not be sufficient if dealing with IE 6 or 7, though they're certainly a good start.


HTML
----

__DOM Nodes__: Old browsers parse HTML more slowly, which can affect time to first paint on load. After the DOM is drawn, large numbers of DOM nodes or deeply-nested nodes can affect performance, especially of JS execution.

__Conditional Comments:__ Unique to IE, these special HTML comments allow you to load chunks of HTML *based on version of IE.* These were a hack graciously added by Microsoft to ease compatibility issues. The look like this: `<!--[if lt IE 8]>CONTENT<![endif]-->`. That's read as "if less than IE 8 then show the word CONTENT". These comments let you do things like loading a different version of jQuery (e.g. 1.x) for old browsers, while still loading a light DOM library (e.g. Zepto) for newer browsers. Modern browsers will ignore these comments entirely.

__Doctype:__ `<!doctype html>` is the right answer. Non-standard or missing doctypes will cause old versions of IE to throw terribly inscrutable XML validation errors.


CSS
----

__Media Queries:__ IE 8 and below have no support for media queries (`@media screen and (max-width: 768px) {`). This would make mobile-responsive design nearly impossible were it not for a few crafy JS polyfills. Of the many available, [Respond.js](https://github.com/scottjehl/Respond) stands out for its small file size and fast performance, though it only reads the most common of media queries, so don't try anything too fancy.

__Modernizr:__ This is the quintessential library for detecting CSS (and HTML and JS) features across all browsers, old and new. If you need to know if gradients or transforms are supported, this is how to do it.

[CSS3Pie](http://css3pie.com/): This library magically polyfills many CSS3 features (e.g. `border-radius`, `box-shadow`) in old browsers, via some really crazy tricks. It's is *all kinds of dangerous,* especially if your site involves any animations at all, but it just might get you out of a tight spot once in a while. *Much* preferable is to design such that any CSS3 features you're taking advantage of degrade tolerably in old versions of IE.

__CSS Expressions:__ These are actually an old feature from IE 6-8 that allowed for dynamically-evaluated logic in stylesheets, not unlike what SASS and LESS now provide. This was removed in IE 9 and above. You're unlikely to see these in the wild, but they're included in this doc as something to be aware of.


JS
----

__Execution Speed__: Old browsers run JS *much* more slowly. As a result, many modern JS MVC frameworks lag terribly on complex pages. Watch out especially for things like client-side search that require the user to wait for the page to change while they're typing.

`requestAnimationFrame`: Not supported until IE 10. This is only a crucial feature if you're building complex animations. Note that most animation libraries use this method under the hood.

`getElementsByClassName()`: Unsupported until IE 9, this is one of the most compelling reasons to use jQuery 1.x (i.e. not 2.x or 3.x) for projects that support older browsers. After jQuery 1.x, the "Sizzle" polyfill library for `getElementsByClassName()` was removed.

`console.log()`: IE 8 and 9 only support `console` when developer tools are open. When they're closed (i.e. when the site is in normal use), `console` is undefined, and any calls to it will crash your JS execution with a "`console` is undefined" error. It's actually the entire `console` object that's missing, including `.warn()`, `.info()`, etc.

__Web Workers:__ These are quite simply missing from older browsers, and are non-trivial to polyfill, since you'd have to move the worker's code execution into the main browser thread, blocking execution of other JS. Avoid workers entirely if you're supporting oldIE.

__Modernizr:__ This is the quintessential library for detecting JS (and HTML and CSS) features across all browsers, old and new. If you need to know if JSON or Flash is supported, this is how to do it.


Other Oddities
--------------

__Concurrent HTTP Requests__: Modern browsers (IE8 and above) can maintain 6 (or sometimes more) open HTTP connections at a time. That means if you have 20 assets (JS, CSS, images) required to render your page, the first six will be requested as soon as those tags in the DOM are parsed, then when one of them finishes, the next in the queue will be requested. IE 6 and 7 have a *much* more restrictive limit of 2 concurrent HTTP connections. That means pages with large numbers of assets will take a very long time to load. AJAX requests are subject to this same limit, so watch out for situations where you might be hitting the server for a large number of AJAXy things.


Testing
-------

[Browserstack](https://www.browserstack.com/): A great site for testing across different browsers. Note that old versions of IE do sometimes vary slightly on different versions of Windows, so truly exhaustive testing requires running each combination, though this is usually overkill.


Tools
-----
[HTML5Boilerplate](https://html5boilerplate.com/): *Awesome* starting template for any project that needs to support old browsers. Custom builds available.

[Modernizr](https://modernizr.com): Browser feature detection. If you only need a few features, you can create a custom build on the Modernizr website.

[CSS3Pie](http://css3pie.com/): Polyfill for some CSS3 features in old browsers. Sometimes magic, sometimes a buggy nightmare. You have been warned.

[Respond.js](https://github.com/scottjehl/Respond): Polyfill for @media queries on IE 8 and below.
