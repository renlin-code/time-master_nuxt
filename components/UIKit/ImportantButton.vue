<template>
  <button class="important-button"
    :class="{'selected' : selected}"
    @click="selected = !selected"
  >
    <flag :color="flagColor" />
  </button>
</template>

<script>
import flag from '../icons/flag.vue';

export default {
  name: "ImportantButton",
  components: {flag},
  data: () => ({
    selected: false
  }),
  computed: {
    flagColor() {
      return this.selected ? "#ffffff" : "#F5805E";
    }
  }
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .important-button {
    width: 150rem;
    height: 70rem;
    display: grid;
    place-content: center;
    border-radius: 30rem;
    background: #ffffff;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    transition: background 360ms ease-in-out;
    &.selected {
      background: $main-color;
    }
  }
</style>
