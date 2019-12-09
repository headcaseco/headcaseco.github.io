<template>
  <ul class="slideshow" ref="slides">
    <li :class="['slide', {'active': currentSlide == i}]" v-for="(slide, i) in slides" :key="i">{{slide}}</li>
  </ul>
</template>

<script>
export default {
  name: 'Slideshow',
  data() {
    return {
        slides: ['management', 'business', 'design', 'advertising'],
        domSlides: {},
        currentSlide: 0,
        intervalid1: null
    }
  },
  mounted() {
    this.initSlideshow()

  },
  computed: {
  },
  methods: {
    nextSlide() {
      // console.log('this.currentSlide', this.currentSlide)
      this.domSlides[this.currentSlide].className = 'slide'
      this.currentSlide = (this.currentSlide+1) % this.domSlides.length
      this.domSlides[this.currentSlide].className = 'slide active'
    },
    initSlideshow() {
      this.domSlides = document.querySelectorAll('.slideshow .slide')
      this.setSlideInterval()
    },
    setSlideInterval() {
      this.intervalid1 = setInterval(() => {
        this.nextSlide()
      }, 2000);
    }
  }
}
</script>

<style scoped>
.slideshow {
  display: inline-block;  
  width: 50%;
  height: 75px;
  position: relative;
  padding: 0px;
  margin: 0px;
  list-style-type: none;
}

.slide {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 100%;
  opacity: 0;
  z-index: 10;

  font-size: 4rem;
  color: #fff;
  box-sizing: border-box;
  text-align: left;
  display: block;
  font-weight: 300;
}
.active {
  opacity: 1;
  z-index: 20;
}

/* Responsive */
@media only screen and (max-width: 600px) {
  .slideshow {
    width: 100%;
  }
  .slide {
    font-size: 3rem;
  }
}
</style>
