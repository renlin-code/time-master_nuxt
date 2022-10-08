<template>
  <button class="ok-button">
    <ok />
  </button>
</template>

<script>
import Ok from '../icons/ok.vue';

export default {
  name: "OkButton",
  components: {Ok}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .ok-button {
    width: 78rem;
    height: 78rem;
    border-radius: 50%;
    background-color: $main-color;
    display: grid;
    place-content: center;
    z-index: 1;
    transform-origin: center;
    cursor: pointer;
    box-shadow: 0px 2px 4px rgba($black, 0.25);
  }
</style>
