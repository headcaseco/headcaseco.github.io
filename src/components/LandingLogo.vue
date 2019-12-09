<template>
  <div class="landing-logo">
    <h1>{{text}}</h1>
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
  padding: 0 1rem;
  margin: 0;
  border: none;
  text-transform: uppercase;
  animation: flicker 1.5s infinite alternate;
  
  opacity: 0;
  transition: all .4s ease-in-out .5s;
}
.landing-logo.show h1 {
  opacity: 1;
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

/* Responsive */
@media only screen and (max-width: 600px) {
  h1 {
   font-size: 5.5rem;
  }
}
</style>
