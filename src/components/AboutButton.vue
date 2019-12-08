<template>
  <transition name="fade">
    <a class="button about-button" v-scroll-to="{ el: '.about-section', duration: 500, easing: 'ease' }" href="#">About</a>
  </transition>
</template>

<script>
import Vue from "vue"
import { ObserveVisibility } from "vue-observe-visibility"
import VueScrollTo from 'vue-scrollto'
Vue.directive("scroll-to", VueScrollTo)
Vue.directive("observe-visibility", ObserveVisibility)
  

export default {
  name: 'AboutButton',
  props: {
      text: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .about-button {
    bottom: 20px;
    right: -20px;
    transform: rotate(90deg);
    visibility: hidden; /*NOTE*/
  }
</style>
