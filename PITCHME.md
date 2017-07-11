# MODULES!
### aka Javascript grows up a wee bit

![cat](https://media.giphy.com/media/Sjj8NXm7E10qs/giphy.gif)

---
# Why Modules?
* Simple!
* Predictable!
* Discoverable!
* Testable!

---
# History

Concat everything into a single file - YOLO!

![cat box](https://media.giphy.com/media/56xijcnShy5sA/giphy.gif)

Note:
* giant payloads with mostly unused code
* hard to reuse basic functions
* end up with lots of duplicate code
* possibly trample globals in your library's name space, eg `noConflict`

---
# Modernity

ECMAScript 2015 (ES6) introduces native module syntax!

```
import foo from 'blah'
...
export default bar
```

But no browser fully implements it yet [1] :(

Until then Webpack, Browserify, Rollup, etc make it possible to leverage module syntax. 

[1] https://jakearchibald.com/2017/es-modules-in-browsers/

---
# What I'm Intentionally Leaving Out

* CommonJS
* AMD
* Your ex coworker's better async module library confusingly called Yet Another Module Library or YAML-DOS

![maru hiding](https://media.giphy.com/media/aA2kuwtG7Xnt6/giphy.gif)

---
# Simple!

Creating a Module
```
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
import cube from './math-utils'

let rateOfChange = cube(4)
```
@[1]

---

# Predictable
  * Partition code
  * Encapsulation

```
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

(show writing a simple test in our codebase)

---

# Performance

(talk about packaging only what you need and show the admin/connections page)
(Webpack 3 unwrapping maybe)
(Tree shaking silliness)

---

# Work Faster

Make it easy to include whole new libraries

---

# Angular's DI and/or/vs Modules

(explain how Angular works and how to use modules with or instead)

---

# Modules vs Components

* Components are a chunk of reusable UI code
* Components use the module syntax to import their dependencies and export their utilities
