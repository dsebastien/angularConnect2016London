# Architecture Panel

Named routes not supported by choice, in order to better support lazy loading (main reason).
They chose for pure URL based routing

Observable is comign to Web browsers but it will take some more time
The main difficulty in learning Rx is not the Observable contract but the vast choice of operators that provide a lot of flexibility but can be daunting.
For the tooling, there are extensions in development to provide better visibility over what an Observable stream is doing.

Guidelines regarding RxJS usage in Angular Apps: pipe or not, and how to choose:
* in general they don't describe "one" way to develop apps
* Victor uses Redux and Rx extensively and uses the async pipe in most cases because they work great
* State management is broad
  * input handling: reactive forms

Large Angular 1 legacy: state of ngUpgrade and experience with using ng1 in ng2 apps
* restrictions:
  * Angular 1 can inject its injectables in the NG2 root injector
  * Each DOM element can only be owned/handled by NG1 or NG2
  * Each framework treats the other as a black box
* they are thinking about

AOT: compiler collects all html css, js and compiles/bundles everything together so that the bundle can be requested in a single shot and fetching is done when 

Redux
* async management isolated in a Redux middleware
* components become simple "render functions"

AOT and JIT
* their goal is (through CLI) to have a pipeline with AOT enabled at all times (for dev and prod alike)
* with JIT the code is eval-ed at runtime in the browser
* they encapsulate the CSS; for now there is duplication of the CSS (e.g., assuming that the same CSS code is used in multiple components)

AOT setup
* biggest gotcha: has to run through the compiler -> works with imports and exports
* library owners have to use ngc (ng compiler) to generate JSON files containing metadata

AOT and decorators
* could be nice but makes it more complex for the AOT compiler & TS to understand what the code does
* bad from a development perspective as it can look like black magic, explicitness should be preferred

Web components support
* tricky parts