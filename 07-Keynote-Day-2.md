# Keynote

## Building blocks
### Components
* @Component decorator: attaching metadata, not changing the behavior of the class
  * Styles: they have a shim of the Shadow DOM spec
* Ng Modules: way to easily regroup, import/export functionality, services, components, styles, etc
* Routing
  * navigation cancellation
  * pre-loading
  * hierarchical navigation
  * router outlets can be nested
  * links: <a routerLink="">Welcome</a>
* Lazy loading
  * linked to routes (Router.forChild, ...)
* Testing
  * TestBed: to easily create components for Testing
  * fakeAsync and tick function: control time
    * helps write tests in a synchronous looking way, while it still executes asynchronously
* Internationalization
  * 

## Build pipeline and Webpack
AOT:
* webpack: @ngtools/webpack
* ngtools.NgcWebpackPlugin

What it does:
* analyze the app within Webpack
* detect routes, see lazy routes, ...
* let webpack build the packages for us

New main entry file (main.aot.ts in the example)
* platformBrowser
* ...

