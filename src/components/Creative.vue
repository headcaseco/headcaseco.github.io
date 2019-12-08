<template>
  <div class="creative">
    <h3>Creative</h3>
    <slot />
    <span>.</span>
  </div>
</template>

<script>
// import WordList from './components/WordList.vue'

export default {
  name: 'Creative',
  components: {
    // WordList
  },
  props: {
      text: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.creative {
  text-align: center;
  margin: 20px 0;
  padding: 0 20px;
  box-sizing: border-box;
  height: 100vh;
  scroll-snap-align: center;

  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-content: stretch;
  align-items: center;
}

h3 {
  padding: 0px;
  margin: 0;
}

h3,
span {
  font-size: 5rem;
  font-weight: 100;
  text-transform: capitalize;
  display: inline-block;
}


@media only screen and (max-width: 600px) {
  .word-list {
    max-width: 350px;
    text-align: right;
  }
  h3 {
    font-size: 3rem;
  }
}
</style>
