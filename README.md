# Vue Drawer

![demo](https://cloud.githubusercontent.com/assets/4466222/16769209/b4dcd3d8-4882-11e6-8c08-bfa52f7636e2.gif)

# Install

```
$ npm install --save vue-drawer
```

# Usage

```html
<drawer :show.sync="drawerShow">
  <div slot="drawer">
    <h2>Drawer</h2>
  </div>
  <center>
    <button v-on:click="drawerToggle">toggle</button>
  </center>
</drawer>
```

```js
import Drawer from '../src/drawer.vue'

export default {
  data() {
    return {
      drawerShow: false
    }
   },
   methods: {
     drawerToggle() {
       this.drawerShow = !this.drawerShow;
    }
   },
  components: { Drawer }
}
```
