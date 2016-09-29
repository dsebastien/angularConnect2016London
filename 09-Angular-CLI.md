# CLI

Scaffolding
* `ng new blabla` (alias for ng init)

How it works:
* Blueprints
  * best practices from the style guide
  * npm dependencies
  * TypeScript and testing configuration
  * environment settings

Parameters:
* dry-run
* Blueprints
* skip-npm
* source-dir
* style
* ...


Generating
* `ng generate`

Can generate:
* cl: class
* c: component
* d: directive
* e: enum
* m: module

Examples:
* `ng generate component header`
* `ng generate module foo --routing`
* `ng generate component path/to/header --flat --spec=false --inline-template --inline-style`

Looks up the tree to find the closest module

Production target:
* minification & uglification
* result written to disk: dist folder

Support for deployment on GitHub pages

Future:
* AOT
* Mobile (PWA)
* Universal
* Refactoring
* Upgrades (major angular versions)
* Addons (deployment, Webpack access)
* Performance
* Library developer mode