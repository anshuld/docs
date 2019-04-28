Waterfall

 - There are a couple of key considerations when looking at waterfall slopes. First, be aware of the scale of the time axis. Tests that run in a short amount of time may sometimes be shown in units of half a second, which would exaggerate the horizontal aspect of slope. Second, keep in mind which requests are most important to the user experience. Many requests may be necessary to construct a usable page. The critical path is the name for the requests that are required to get the page to this state. The slope of the critical path should always be as vertical as possible. In contrast, the slope of requests outside of the critical path should be second in priority.
 - Tools like Webpack Bundle Analyzer, Source Map Explorer and Bundle Buddy allow you to audit your bundles for opportunities to trim them down.


 Lighthouse video

 - Minification
 - Compression -- akamai??
 - Cache opportunities
 - Unused code - dev tools code coverage - load and runtime, lighouse coverage audit, test for visual regression
 - Optimizing the critical rendering path
 - Auditing javascript bundles - webpack bundle analyzer, Bundle phobia, VS - import cose
 - tree shaking
 - code splitting
 - TTI - LABS (SYNTHETIC testing), FID - RUM


Concepts:
- By default, JavaScript execution is "parser blocking"

 Udacity Course

 - Incremental html delivery
 - css specific rule
 - css display none on a DOM object - means node won't be added to te render tree
 - media query on the link tag - technique to reduce render blocking css
 - javascript is parser blocking
 - css is render blocking, but it blocks javascript execution as well as the browser doesn't execute javascript until the csssom has been built
 - javascript that doesn't modify DOM or CSSOM should not block rendering
 - async attribute on script allows it to not block the dom construction and also when the script has been loaded, it's execution does not wait for completion of cssom
 - For inline scripts, put these above css to stop it blocking on cssom
