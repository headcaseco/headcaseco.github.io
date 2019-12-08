<template>
  <ul id="slides" class="slideshow" ref="slides">
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
      this.domSlides = document.querySelectorAll('#slides .slide')
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
  /*scroll-snap-align: end;*/
  /*width: 100%;*/
  display: inline-block;  
  width: 50%;
  height: 100px;
  position: relative;
  padding: 0px;
  margin: 0px;
  list-style-type: none;
}

.slideshow:after {
    content: '';
    position: absolute;
    left: 0; 
    bottom: -4px;
    height: 4px;
    background-color: #fff;
    width: 0;
    transition: width .25s;
    width: 100%;
  }


.placeholder {
  opacity: 0;
}

.slide {
  position: absolute;
  left: 0px;
  top: 0px;
  width: 100%;
  height: 100%;
  opacity: 0;
  z-index: 10;

  font-size: 80px;
  color: #fff;
  box-sizing: border-box;
  text-align: center;
  display: block;

}

.active {
  opacity: 1;
  z-index: 20;
}
</style>
