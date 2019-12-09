<template>
  <a class="button social" href="https://instagram.com/czllnr" target="_blank">Instagram</a>
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

<style scoped>
  .social {
    bottom: 0px;
    left: 60px;
    transform-origin: bottom left;
  }
  .social.show {
    transform: rotate(-90deg);
  }
</style>
