## Notes from workshop at Akamai Office 

Find blocking scripts, make things fast (no throttle) to rule out network issues, so can focus on script evaluation
FID first input delay - can be used to check if user is being delayed by a slow script execution

From Networking discussion - 

- write a script that loads non critical scripts, after 5 seconds - if these scripts are the hindrance to TTI
- visual optimizer to find duplicate in the bundle
- talking to 3rd party isn't easy - onetrust were not friendly with thesun
- hosting 3rd party script on our domain will reduce round trip time

=============================================

## Other Random Notes

- Device Market share uk - android ios 50% appx
- cpu, battery other factors
- bandwidth isn't the bottleneck (often)
- latency (rtt) has huge impact - varies by distance, other factors - router, - network
- TLS - smaller certificate the chain, the better - qualys ssl checker
- ocsp stapling - workaround ocsp checks - akamai supports it - pick your - certificate provider carefully
- hsts, but can break site (if resource on http) - hstspreload.org
- fonts - prioritasation
- http 1.1 does keep alive by default
- high performance browser networking - llyas
- tcp - starts slower - small no. of packets 15KB in one rtt
- Initial congetion window - For better rendering - send your CRT resources - within 15K, although some CDN have higher limits
- reduce rtt as much - brotli - another 20% compression - more cpu though
- minification - 5% benefit
- Chrome priority - affects download order - hueristics based - higher in <head>, images - low, fonts - higher. Diff browser have different, also on - http 1 or 2, in 2 hints given - server decides
- no preload - @import in css, document.write of external resource
- initial congestion window akamai
- css - mdeia query 
  or bundle together 
  critical css - but may need repainting and maintanence
50K js - split each bundle - executon can start early
js - async - not recommended anymore
js - defer - better - order, keep it towards end of body tag
js - WHATWG - great visual reminder 
tree shaking, code spltting - webpack
visualise bundle - same 6K line repeated in same bundle - node source map explorer
third party sometimes sourcemap is included in the bundle - base 64 encoded
webfont block text rendering (but not imgs) - render tree - fonts and imgs are discovered 
font-foundry - gives u right version
UK/EU customers - subset fonts (have only neglish glyphs)
third party - preconnect - don't overuse - limit 6 - analytics, tag manager, marketing critical ones - can be http header based hints
cloudry to host images
andydavis.me blog
use rel=preload carefully - not a hint, preconnect is
prefetch - download at idle time at end of page - feature flag, mark edmondsoon used google analytics before  - 50% right
avoid split request accross hosts - join.thetime, login.thetimes
no image sprites - cpu pressure - low devices throw away uneeded images - instead go to svg
inline small objects - avoid
http/2 binary, multiplexing, header compression, same stream reused - prioritesed based on weight and dependencies
ishttp2fast.yet.com
prioritisatoin works only on one host - host 3rd party useself - http2, caching benefit - facebook did a study and found not much, safary will keep 2 copies of jquery for e.g.
cache control - public for news thetimes
cache control - immutable, stale-while-revalidate
cache control- edge nodes most effective
cache  - service worker, offline
choreograph the content - divide into parts - content, enhancement,leftover - defer tags - chat even before page loaded?
lazy loading images - pick carefully
IntersectionObserver
free the main thread - webworkers, requestidlecallback, requestAnimationFrame
webworker - can't inetract with dom
images loading, decoding = sync, async, delaying decode frees main thread
jpeg lossy compression baseline, progressive
png gif - lossless compression
images should be optimised
srcset
picture element
responsivebreakpoints.com
replace css with images
icon fonts - use svg (won't block rendering)
svg can be optimised too
svg good for charts
tympanus.net
image manager - same domain benefit - less rtt
image manager - srcset still makes difference
webspeedtest.cloudinary.com

measure performance - 
lighthouse is opinionated - should be in a consistent environment
many people use newrelic
chrome - performance start in guest mode (excludes extensions)
optimizely.com
for ios use safari on osx - also has timeline, not as granularity as chrome

network control - network link conditionar - osx
to find blocking scripts, make things fast (no throttle) to rule out network issues, so can focus on script evaluation
look for patterns in timeline - script loading scripts loading other scripts


TTI can be misleading - 5 seconds cpu idle is harsh - might not be needed for some sites
speed index - is very sensitive - can screw up if page renders a bit later its sensitive to visual nature

Typical things to look at - 
server response
domcontentloaded
first input delay
first cpu idle
onload as pseudo metric

time based budget, not size based
make performance public - perfbar in uat?



guypo.com
ishttp2fast.yet.com
telegraph blog audit tags
responsivebreakpoints.com
squoosh.app
perfbar
andydavies.me


easy bits 
preconnect on the right resource
set bgcolour and then image - good user experience
























priority - how to control
document.wirte - how to detect






