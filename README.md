# vue-simple-modal

A Vue component that shows a modal.


## Installation

```js
npm i --save-dev vue-simple-modal
```

### Browser

Include the script file, then install the component with `Vue.use(VueClock);` e.g.:

```html
<script type="text/javascript" src="node_modules/vuejs/dist/vue.min.js"></script>
<script type="text/javascript" src="node_modules/vue-simple-modal/dist/vue-modal.min.js"></script>
<script type="text/javascript">
  Vue.use(VueModal);
</script>
```

### Module

```js
import VueModal from 'vue-modal';
```

## Usage

Once installed, it can be used in a template as simply as:

```html
<button @click="toggleModal">toggle modal</button>
<vue-modal :show="showModal" @close="toggleModal"></vue-modal>
```
