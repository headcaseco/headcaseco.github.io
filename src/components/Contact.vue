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

<style scoped>
  .contact {
    right: 60px;
    bottom: 0px;
    transform-origin: bottom right;
  }
  .contact.show{
    transform: rotate(90deg);
  }
</style>
