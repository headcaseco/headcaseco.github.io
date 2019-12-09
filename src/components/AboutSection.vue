<template>
  <div v-observe-visibility="aboutInView" :class="['about-section',{'in-view': showAbout}]">
    <p>Headcase is an equity metrics sales facebook return on investment user experience crowdfunding partnership MVP monetization business model canvas launch party stealth growth hacking. Ecosystem disruptive early adopters vesting period pitch freemium android interaction design gamification. User experience advisor graphical user interface iteration investor. Bandwidth entrepreneur startup gamification backing ecosystem validation.</p>
  </div>
</template>

<script>
  import Vue from "vue"
import { ObserveVisibility } from "vue-observe-visibility"
Vue.directive("observe-visibility", ObserveVisibility)

export default {
  name: 'AboutSection',
  props: {
      text: String
  },
  data() {
    return {
      showAbout: false
    }
  },
  methods: {
    aboutInView(isVisible) {
      /* eslint-disable no-console */
      this.showAbout = isVisible
      console.log("this.showAbout", this.showAbout, "isVisible: ", isVisible)
      /* eslint-disable no-console */
    }
  }
}
</script>

<style scoped>
.about-section {
  height: 100vh;
  margin: 0 auto;
  box-sizing: border-box;
  scroll-snap-align: end;

  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-content: stretch;
  align-items: center;
}
p {
  font-size: 1.5rem;
  line-height: 1.5;
  letter-spacing: 1.5px;
  text-align: justify;
  max-width: 600px;
  padding: 0 20px;
  transform: translateY(10%);
  opacity: 0;
  transition: all .6s ease-in-out .5s;
}
.in-view p {
  transform: translateY(0);
  opacity: 1;
}

/* Responsive */
@media only screen and (max-width: 600px) {
  .about-section {
    max-width: 100%;
    text-align: right;
  }
}
</style>
