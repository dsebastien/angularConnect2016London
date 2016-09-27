# Rescue Mobile Experience

* Latency is the enemy: 53% of mobile site visits are abandoned if pages take longer than 3 seconds to load
* 3 out of 4 mobile sites take longer than 10 seconds to load

RAIL guidelines:
* R: respond with 100ms
* A: animate at 60fps
* I: idle time for low priority work
* L: load content in under 1000ms

Aggressive target but great for user experience. Applied at Google.

* Shell: first contact with the user
  * state of the app before the JS code executes
    * load index.html
    * parse index.html
    * create & render DOM + fetch JS/css as discovered then execute JS
  * application shell is critical for user perception
    * advice: use Angular Universal (server side rendering)
* Load: getting resources on the device
  * transfer less code
  * install like a native app with Service Worker

@angular/app-shell
* *shellRender
* *shellNoRender

Service workers: @angular/service-worker
* Require worker-basic.min.js ...
* ngsw-manifest.json:
 ```
    {
        "static": {
            "urls": {
                "/index.html": "ae543...",
                ...
            }
        }
    }
 ```
  * the service worker of angular uses that to check whether it has the latest code or not
  * the manifest can be generated by a Webpack plugin provided by the angular team: angular-wpplugin

Initial data best practices:
* request above the fold data early
* initial data in index.html
* cache data intelligently
* pay careful attention to initial state

Coming soon: SW dynamic caching

Oppotunities for re-engagement:
* install to homescreen
* push notifications
  * back-end -> push service -> service worker
  * ng service worker supports push notifications (showNotifications: true)
  * npm install --save web-push
    ```
        const webPush = require("web-push");
        webPush.setGCMAPIKey(...);
        let payload = { ... };
        webPush.sendNotification({ payload: new Buffer(JSON.stringify(...))});
    ```
  * ...

* Docs coming to mobile.angular.io
* Return of mobile support in the CLI
* App shell support for other build systems
* Tighter integration between Angular and service worker
* slides will be available via twitter.com/synalx