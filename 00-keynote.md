# Keynote

Important:
* Final/stable release available.
* Now uses semantic versioning
* Release cadence
  * 6 months between each major release
* stable APIs remain stable but they'll have a deprecation policy (announce in advance)
  * documentation states whether the API is stable, unstable or deprecated

Angular Core:
* declarative templating
* change detection
* dependency injection
* ...

Angular Extensions:
* Angular Material
* i18n
* Router
* Forms
* Animations
* ngUpgrade

Dev tools:
* Angular CLI
* Protractor
* Angular Augury
* Language Services

Performance:
* size: smaller size, lazy loading
* speed: be faster, do less, memory pressure, multi-threading

Build step
* HTML/css/.. ->offline compiler -> inline modules (concat) -> tree shaking -> minification

Minification is not always safe (e.g., property names)

MyAppModule (components, pipies, providers, ...)
* each can depend on different modules

Change detection:
* in Angular 1: needed to run multiple times until stability is reached
* in Angular 2: goes from the top of the tree and down, in a single pass. Pars of the tree can be pruned as the algorithm goes through it
  * strategies: detach a sub-tree, ...
  * there are hooks (before/after child checks, etc)

Multi-threading:
* leverage web workers to execute as much code as possible in separate "threads"

Benchpress:
* tool to measure the performances (gc pressure, execution time, render time, update speed, ...)

Mobile cannot be ignored, it is pervasive.
* Angular 2 supports mobile scenarios
* Angular 2 can be combined with NativeScript to create native experiences on multiple mobile platforms (Android, iOS, ...) with much less effort

Desktop is still there
* Angular 2 can be combined with Electron to provide a good desktop experience: chrome, file system access, native notifications, etc

