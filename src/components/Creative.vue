<template>
  <div class="creative">
    <h3>creative</h3>
    <slot />
  </div>
</template>

<script>


export default {
  name: 'Creative',
  props: {
      text: String
  }
}
</script>

<style scoped>
.creative {
  text-align: center;
  box-sizing: border-box;
  height: 100vh;
  scroll-snap-align: center;
  overflow: hidden;

  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-content: stretch;
  align-items: center;
}

h3 {
  font-size: 4rem;
  font-weight: 100;
  display: inline-block;
  padding: 0px 20px 0px 0px;
  box-sizing: border-box;
  margin: 0;
  width: 50%;
  text-align: right;
  font-family: var(--body-font);
  font-weight: 600;

  transition: .6s all ease-in-out .5s;
  transform: translateY(-50%);
  opacity: 0;
}
.creative.show h3 {
  transform: translateY(0%);
  opacity: 1;
}



/* Responsive */
@media only screen and (max-width: 750px) {
  .creative {
    flex-direction: column;
  }
  h3 {
    font-size: 3rem;
    text-align: left;
    width: 100%;
    padding-right: 0;
    padding-left: 20px;
  }
}
</style>
