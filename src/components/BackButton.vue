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

<style scoped>
  .back-button {
    top: 10px;
    left: -10px;
    transform: rotate(-90deg);
    visibility: hidden; /*NOTE*/
  }
</style>
