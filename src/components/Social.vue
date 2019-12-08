<template>
  <a class="button social" href="https://instagram.com/headcase">Instagram</a>
</template>

<script>
export default {
  name: 'Social',
  props: {
    text: String,
    show: Boolean
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .social {
    bottom:  0px;
    left: 0px;
    /*transform: rotate(-90deg);*/
  }
</style>
