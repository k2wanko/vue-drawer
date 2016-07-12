<template>
  <div class="vue-drawer">
    <div class="main">
      <slot></slot>
      <div class="scrim" v-bind:class="show ? 'scrim-enter' : ''" v-touch:tap="scrimTouch"></div>
    </div>
    <div class="drawer" v-bind:class="show ? 'drawer-enter' : ''" v-bind:style="{width: drawerWidth}">
      <slot name="drawer"></slot>
    </div>
  </div>
</template>

<script>
 import Vue from 'vue'
 import VueTouch from 'vue-touch'

 Vue.use(VueTouch);
 
 export default {
   props: {
     show: {
       type: Boolean,
       twoWay: true
     }
   },
   data() {
     return {
       drawerWidth: '256px'
     }
   },
   methods: {
     scrimTouch() {
       this.show = false;
     }
   }
 }
</script>

<style>
 .vue-drawer {
   display: block;
   position: absolute;
   top: 0;
   left: 0;
   width: 100%;
   height: 100%;
   overflow: hidden;
 }

 .vue-drawer > .main {
   position: absolute;
   top: 0;
   left: 0;
   right: 0;
   bottom: 0;
 }

 .vue-drawer > .main > .scrim {
   position: absolute;
   top: 0;
   left: 0;
   right: 0;
   bottom: 0;
   visibility: hidden;
   opacity: 0;
   transition: opacity ease-in-out 0.38s, visibility ease-in-out 0.38s;
   background-color: rgba(0, 0, 0, 0.3);
 }

 .vue-drawer > .main > .scrim-enter {
   visibility: visible;
   opacity: 1;
 }

 .vue-drawer > .drawer {
   background-color: #fff;
   position: fixed;
   left: 0;
   top: 0;
   width: 100%;
   height:100%;
   overflow: hidden;
   pointer-events: none;
   transform: translateX(-102%);
   transition: transform ease-in-out 0.38s;
   will-change: none;
 }

 .vue-drawer > .drawer-enter {
   transform: translateX(0%);
 }
</style>
