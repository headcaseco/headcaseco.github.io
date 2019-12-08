<template>
  <div class="landing-logo">
    <h1 class="unica" style="font-weight: 100;">{{text}}</h1>
  </div>
</template>

<script>
export default {
  name: 'LandingLogo',
  props: {
      text: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.landing-logo {
  height: 100vh;
   display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  align-content: stretch;
  align-items: center;
  scroll-snap-align: start;
}

h1 {
  font-size: 8rem;
  font-weight: 100;
  padding: 1rem;
  margin: 0;
  border: none;
  text-transform: uppercase;
  /*margin: 300px 0;*/
  animation: flicker 1.5s infinite alternate;
}

h1::-moz-selection {
  color: var(--neon-text-color);
}

h1::selection {
  color: var(--neon-text-color);
}

h1:focus {
  outline: none;
}

@media only screen and (max-width: 600px) {
  h1 {
   font-size: 5rem;
  }
}

/* Animate neon flicker */
@keyframes flicker {
    
    0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
      
        text-shadow:
            -0.2rem -0.2rem 1rem #fff,
            0.2rem 0.2rem 1rem #fff,
            0 0 2rem var(--neon-text-color),
            0 0 4rem var(--neon-text-color);
    }
    
    20%, 24%, 55% {        
        text-shadow: none;
        box-shadow: none;
    }    
}
</style>
