# Angular 2 compiler

## Slides
g.co/ng/ac16-compiler


## Being fast means
* page load
* switching from a route to another
  * destroy the DOM and recreate it
  * benchmark: deep tree benchmark
* update values

## Inputs
* component metadata
  * template
    * {{}} interpolation, event bindings, etc
  * directives
  * other types of inputs/outputs: NgModule, Pipe, Input, Output, ContentChildren, ViewChildren, HostBinding, ...

## Template parser
Read the template and builds an AST

For the bindings:
```
{
    text: "",
    expr: {
        propPath: ["user", "name"],
        line: 2,
        col: 14
    }
}
```

This is the representation of a binding in the AST.

Parsers that can be used to parse the templates:
* Web browser: cannot output what angular wants/needs. Prevents the server side rendering use cases
* JavaScript parser instead

## Template instantiation 101
Fastest way to create a DOM element:
* element.innerHTML = '<form>...' (slowest)
* var clone = element.cloneNode(true) (fastest now)
* document.createElement(...) (very close to the speed of cloneNode)

A view is an instance of a template

## Template instantiation 201
Optimize the data structures

in class NgElement, the map of directives (type -> instance map) could be a source of slowness (performance impact of instanciating, adding to the map, reading from it, ...).
They refactored the data structure and it made it possible to leverage the JS VM optimizations (fast property access with hidden classes).

Next they tried to recycle DOM nodes and object instances, added a cache (ViewCache), etc.

The ViewCache was a problem because it meant that going from a route to another route meant that the previous route was in the cache, which had an impact.

## Template instanciation 301
Previous View Class

They refactored to have fast property access everywhere...

Added class CompileElement

## JIT Compilation
Compile in the browser:
* inputs -> parse & generate -> View Source -> Eval -> View Class generated -> new ...() -> Running app

Problems:
* parse & generate in the browser: takes time and parser needs to be in the browser (bigger and bigger)
* eval is evil: problematic for security (CSP for the win)
* minifcation: can rename variables, can rename properties on object, but it's difficult to know where those are used (closure compiler supports enhanced minification)

## AOT
* on the server: inputs -> parse & generate -> view source
* in the browser: script -> view class -> new ...() -> running app

Better:
* no more eval
* minification better supported since the View class is generated during the compilation step, thus is also minified, meaning that names used in templates remain valid (since the template gets compiled into the ViewClass which is also minified)

## AOT TypeScript output
* inputs -> parse & generate -> View Source (Output AST) -> serialize (View Source for Eval with ES5) or (TS code) or (ES2015)

The AOT compiler comes before the TypeScript compiler. It generates TS code

## AOT Compilation - Metadata collection
They extract metadata on classes (e.g., component, directive, ...) and add it to the AST.

## Usage
```
ngc -p <project>
```

## What's next
Goal: smaller than 10kb
Be Faster Than baseLine
