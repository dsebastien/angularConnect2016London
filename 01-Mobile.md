# Mobile apps

Progressive Web Apps: Web apps that feel like native apps

Tooling around:
* Pure Web apps
* Ionic
* NativeScript

No one-size-fits-all

State of Mobile
* Distribution: how users get the apps
  * search-ability
    * pre-rendering with Angular Universal helps with SEO even if modern search engines can render SPAs and actually index the content in many cases
    * hybrid and native JS app content can be indexed assuming that these are backed by URLs
    * mobile OS's provide OS-level search and app store search
      * with Web apps, we can not appear in app store search
      * public web app content may appear in native OS-level search
        * you might need a hybrid or native app if
          * users should be able to discover your app through app stores
          * ...
  * share-ability
    * developer share targets vs user share targets
    * no share intent handling yet (github.com/mgiuca/web-share/blob/master/docs/explainer.md
    * Hybrid and Native: use plugins for Ionic/cordova/native script to easily integrate content sharing
    * web app sharing is currently limited to Web APIs, no handling of shares from other apps
  * first use experience ability
    * installation = friction for users
  * update ability
* Capabilities
  * Hybrid/Native and access to additional APIs. Examples:
    * Native behaviors
      * No push notifications for iOS Web
      * Bluetooth in Chrome soon, no iOS Web timeline
    * Device features
      * Battery and network info not available in iOS Web
      * Full offline and full-screen possible everywhere, not ideal with iOS Web
      * More A/V camera support...
      * Geo-fencing: not there yet for Web
      * Offline storage and payments everywhere
      * No contacts or calendar access from Web
* Performance
  * 60fps achievable everywhere
* Productivity
  * Testability
