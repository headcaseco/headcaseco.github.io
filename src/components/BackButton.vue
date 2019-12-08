<template>
  <a class="button back-button"  href="mailto:chelsi@headca.se">Back</a>
</template>

<script>
export default {
  name: 'BackButton',
  props: {
      text: String,
      show: Boolean
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  a {
    top: 10px;
    left: -10px;
    transform: rotate(-90deg);
    visibility: hidden; /*NOTE*/
  }
</style>
