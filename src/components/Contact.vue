<template>
  <a class="button contact" href="mailto:chelsi@headca.se">Contact</a>
</template>

<script>
export default {
  name: 'Contact',
  props: {
    text: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  a {
    right: 0px;
    bottom: 0px;
    /*top: 20px;*/
    /*transform: rotate(90deg);*/
  }
</style>
