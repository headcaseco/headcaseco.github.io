<template>
  <div id="app">
      <LandingLogo text="Headcase" :class="[{'show': showLogo}]" v-observe-visibility="logoInView"/>
      
      <Creative :class="[{'show': showSlideshow}]" v-observe-visibility="slideshowInView">
        <Slideshow />
      </Creative>

      <BackButton :class="[{'show': showButtons}]"/>
      <AboutButton :class="[{'show': showButtons}]" />
      <Social :class="[{'show': showButtons}]" />
      <Contact :class="[{'show': showButtons}]"/>

      <AboutSection/>      
  </div>
</template>

<script>
import Vue from "vue"
import { ObserveVisibility } from "vue-observe-visibility"
import VueScrollTo from 'vue-scrollto'
Vue.directive("scroll-to", VueScrollTo)
Vue.directive("observe-visibility", ObserveVisibility)

import LandingLogo from './components/LandingLogo.vue'
import Creative from './components/Creative.vue'
import AboutSection from './components/AboutSection.vue'
import Slideshow from './components/Slideshow.vue'

import Contact from './components/Contact.vue'
import BackButton from './components/BackButton.vue'
import AboutButton from './components/AboutButton.vue'
import Social from './components/Social.vue'

export default {
  name: 'app',
  components: {
    LandingLogo,
    Creative,
    AboutSection,
    Contact,
    Slideshow,
    BackButton,
    AboutButton,
    Social
  },
  data() {
    return {
      showButtons: false,
      showLogo: false,
      showSlideshow: false
    }
  },
  methods: {
    logoInView(isVisible) {
      this.showButtons = !isVisible
      this.showLogo = isVisible
      /* eslint-disable no-console */
      console.log('this.showButtons', this.showButtons, 'this.showLogo ', this.showLogo ,'isVisible', isVisible)
      /* eslint-disable no-console */
    },
    slideshowInView(isVisible) {
      this.showSlideshow = isVisible
            /* eslint-disable no-console */
      console.log('showSlideshow', this.showSlideshow)
      /* eslint-disable no-console */
    }
  }
}
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Exo+2:200i);
@import url('https://fonts.googleapis.com/css?family=Amiko|Barlow+Semi+Condensed|Fira+Code|IBM+Plex+Mono|Julius+Sans+One|Overpass+Mono|Rajdhani|Source+Code+Pro|Unica+One&display=swap');

:root {
  /* Set neon color */
  --neon-text-color: #fff;
  --header-font: 'Unica One', sans-serif;
  --body-font: 'Helvetica', sans-serif;
}

html {
  scroll-snap-type: y mandatory;
}

body {
  font-family: var(--body-font);
  background: #000;
  color: #fff;
  margin: 0;
}

h1,h2,h3,h4,h5 {
  font-family: var(--header-font);
}

.about-section,
.creative,
.landing-logo {
  margin: 20px auto;
}

.button {
  position: fixed;
  z-index: 900;
  text-transform: lowercase;

  padding: 20px;
  transition: all .4s ease-in-out;
  text-decoration: none;
  underline: none;
  color: #fff;
  opacity: 0;
}
.button.show{
  opacity: 1;
}
.button:hover{
  opacity: .5;
}

</style>
