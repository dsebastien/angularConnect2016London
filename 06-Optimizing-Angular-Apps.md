# Optimizing Angular Apps

## tools
* source-map-explorer (npm): analyze code based on sourcemaps

## ES modules
ES modules allow tooling to analyze code dependencies

## Tree shaking
Analyze the module dependencies and identify unused code: not included in the output bundles.

Amdahl's law: theoretically [shrinking] of the [size] of the whole [binary] is limited by the part that doesn't get shrinked.

## AOT
* compile templates before bundling
* huge app startup improvement
* huge runtime performance improvements
* no need to ship the compiler code (size & security improvement)
  * security: no way to embed user input in templates

## Not Quite Ready Yet

Static types allow more optimization
* safely* mangle all names (incl properties)
* inline functions & methods
* constant folding + dead code elimination

Closure compiler:
* high quality, type based optimizer & bundler
* renames, inlines, removes dead code
* bundles & flattens modules
* JSDoc based type annotations

ngc (AoT) -> tsickle -> closure
-> tsicke ("ts2cl") adds Closure JSDoc and Converts TS code

This allows to minify all the names.

Some complexity to deal with:
* Must not rename external symbols (browser symbols, uncompiled libraries, ...)
* 