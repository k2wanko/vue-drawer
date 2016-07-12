<template>
  <drawer :show.sync="drawerShow" :right="drawerRight">
    <div slot="drawer">
      <h2>Header</h2>
      <ul>
        <li v-for="item in navItems">{{item}}</li>
      </ul>
    </div>
    <center>
      <button v-on:click="drawerFlip">flip</button><br>
      <button v-on:click="drawerToggle">toggle</button>
    </center>
  </drawer>
</template>

<script>
 import Drawer from '../src/drawer.vue'
 export default {
   data(){
     return {
       drawerRight: false,
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
     drawerFlip() {
       this.drawerRight = !this.drawerRight;
     },
     drawerToggle() {
       this.drawerShow = !this.drawerShow;
    }
   },
  components: { Drawer }
 }
</script>
