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
* concat everything into a single file
* WHAT COULD GO WRONG?

![cat box](https://media.giphy.com/media/56xijcnShy5sA/giphy.gif)

Note:
* giant payloads with mostly unused code
* hard to reuse basic functions
* end up with lots of duplicate code
* possibly trample globals in your library's name space, eg `noConflict`

---

# Simple!

(add some code about how to make a module, syntax)

---

# Predictable
  * Partition code
  * Encapsulation

(add some code that shows how encapsulation works)

---

# Discoverable
 * Easy to find source
 * Compatible with good tools

(demo the linkage with the editor)

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
