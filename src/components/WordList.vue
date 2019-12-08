<template>
  <div class="word-list">
    <p class="underline">word list</p>
  </div>
</template>

<script>
export default {
  name: 'WordList',
  props: {
      words: Array,
      default: () => []
  }
}
</script>

<style scoped>
.word-list {
  text-align: center;
  padding:  0 20px;
  margin: 20px 0;
  display: inline-block;
}

.underline {
  width: 13rem;
  position: relative;
  /*height: 12px;*/
}

.underline:after {
  position: absolute;
  content: '';
  height: 2px;
  bottom: -4px; 
  background-color: #fff;
}
</style>
