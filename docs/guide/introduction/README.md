# Installation
Use either `npm` or `yarn` to add the package to your project
```js
// npm
npm install vue-typeahead-bootstrap

// yarn
yarn add vue-typeahead-bootstrap
```

Import and register the component

```js
import VueTypeaheadBootstrap from 'vue-typeahead-bootstrap'

// Global Registration
Vue.component('vue-typeahead-bootstrap', VueTypeaheadBootstrap)

// Or Local registration
export default {
  components: {
    VueTypeaheadBootstrap
  }
}
```