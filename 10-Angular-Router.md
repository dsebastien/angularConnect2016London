# How to be lazy with the Angular Router

## Status of Angular Router
* stable: http://bit.ly/2dnFqGi
* docs available
* no breaking changes to expect

## Overview
Role:
* update the URL
* update the component tree
* update the router state based on the URL

## Lazy Loading
* Key capability of the new router
* Transparent
* Links or navigations keep working
* Synchronous link generation

## Preloading
Can implement a PreloadingStrategy
* preload method with route:Route, load:Function and returns an Observable
* register the strategy
  * list it as a provider
* ...

Preloading is:
* Transparent
* pluggable
* platform-specific Preloading
* user-specific preloading

## Bundling