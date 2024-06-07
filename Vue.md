# Vue

JS framework for building user interfaces. Builds on HTML, CSS, and JS.

Declarative, component-based programming model specifically made for user interfaces.

Core Features:
* Declarative Rendering: Vue adds declarative syntax to HTML to update HTML based on JS state.
* Reactivity: Vue tracks JS state changes and automatically updates the HTML.

Vue can be used in serveral different ways:
https://vuejs.org/guide/extras/ways-of-using-vue.html
* Desktop, mobile, WebGL, even terminal apps
* As a single page application
* For static site generation
* Etc...

HTML vs. SFC
* Vue can be used in an HTML file without a build step (convenient).
* Vue can also be in an SFC (must be built into an HTML first though).
  * Advantage: Easier

Vue components are written in an HTML-like format called **Single-File Component**:
* Extension `.vue`
* SFCs contain javascript, HTML, and CSS all in one file for each component:
  * Javascript in the `<script>` tag
  * HTML in the `<template>` tag
  * CSS in the `<css>` tag

Vue has two different ways of writing its JS portion: The Options API and the Composition API.

**Options API:** Component logic is defined with several options (three in example).
* `data`: A function that returns a dictionary (defines object state and default values)
* `methods`: A block of methods that can be called in the component's script
* `mounted()`: A function that runs when the component is 'mounted' (there are several of these types of functions (called "hooks"))

**Composition API:** Component logic is defined is defined in a freeform manner.
* `<script setup>` tells Vue to export all functions and variables declared in the file.
* It eliminates the need to surround the code in `export default { }` and return variables in `setup()`.
  * `export default` allows variables and functions to be used when importing a file without explicitly specifying the variable or function's name.
* Any variables and methods in the script are exported, so they can be used within the template immediately.
* Hooks are still available:
  ```js
  onMounted(() => {
    console.log("Hello World!");
  });
  ```