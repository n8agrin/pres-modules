# MODULES!
### aka Javascript grows up a wee bit

![cat](https://media.giphy.com/media/Sjj8NXm7E10qs/giphy.gif)

---
## Why Modules?
* Simple!
* Predictable!
* Discoverable!
* Testable!

---
## History

Concat everything into a single file - YOLO!

![cat box](https://media.giphy.com/media/56xijcnShy5sA/giphy.gif)

Note:

* giant payloads with mostly unused code
* hard to reuse basic functions
* end up with lots of duplicate code
* possibly trample globals in your library's name space, eg `noConflict`

---
## Modernity

ECMAScript 2015 (ES6) includes native module syntax!

```
import foo from 'blah'
...
export default bar
```

But no browser fully implements it yet [1] :( 

[1] https://jakearchibald.com/2017/es-modules-in-browsers/

Note:

Until then we have:
+ Webpack
+ Browserify
+ Rollup 

---
#### What I'm Intentionally Leaving Out

* CommonJS
* AMD
* Your ex coworker's better async module library confusingly called Yet Another Module Library or YAML-DOS

![maru hiding](https://media.giphy.com/media/aA2kuwtG7Xnt6/giphy.gif)

---
# Simple!

Creating a Module
```
//-- powers.js
function cube (n) { 
  return Math.pow(n, 3)
}

export default cube
```
@[5]

---
# Simple!

Consuming a Module

```
import cube from './powers'

let rateOfChange = cube(4)
```
@[1]

---
# Predictable
  * Partition code
  * Encapsulation

```
//-- powers.js
function powers (base) {
  return function (n) {
    return Math.pow(n, base)    
  }
}

let square = powers(2)
let cube = powers(3)

export {square, cube}
```

---
# Discoverable
 * Easy to find source
 * Makes tooling better

(demo this!)

![Mari](https://media.giphy.com/media/Ww6Hdz0L3CxfW/giphy.gif)

--- 
# Testable
* Modules are singletons
* Easy to mock

```
//-- my_complex_controller.test.js
import {cube} from './powers'
import myComplexCtrl from './my_complex_controller' 
 
describe('my controller', function() {
  beforeEach(function() {
    spyOn(cube)
  })
  it ('should call cube', function() {
    myComplexCtrl.doWork()
    expect(cube).toHaveBeenCalled()
  })
})

```

---
# Performance

* Allows bundlers to build exactly the code used
* ES6 module syntax provides for extra neat optimizations (Tree shaking)

(demo!)

---

# Work Faster

* Easier to reason about small parts of the app
* Try out new technologies
* Refactor without fear

![maru slo mo](https://media.giphy.com/media/W2MbjG64qkiMo/giphy.gif)

---

# Angular's DI and/or/vs Modules

(explain how Angular works and how to use modules with or instead)

---
# Questions?
