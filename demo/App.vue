<template>
  <drawer :show.sync="drawerShow">
    <div slot="drawer">
      <h2>Header</h2>
      <ul>
        <li v-for="item in navItems">{{item}}</li>
      </ul>
    </div>
    <center>
      <button v-on:click="drawerToggle">toggle</button>
    </center>
  </drawer>
</template>

<script>
 import Drawer from '../src/drawer.vue'
 export default {
   data(){
     return {
       drawerShow: false,
       navItems: [
         'Item1',
         'Item2',
         'Item3',
         'Item4',
         'Item5'
       ]
     }
   },
   methods: {
     drawerToggle() {
       this.drawerShow = !this.drawerShow;
    }
   },
  components: { Drawer }
 }
</script>
