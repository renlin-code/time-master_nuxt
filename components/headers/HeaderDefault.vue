<template>
  <div class="header">
    <div class="header__content main-content-wrapper">
      <button class="header__burger"
        @click="openMenu"
      >
        <burger />
      </button>
      <button class="header__search">
        <search />
      </button>
    </div>
  </div>
</template>

<script>
import burger from '../icons/burger.vue';
import search from '../icons/search.vue';

export default {
  components: {burger, search},
  methods: {
    openMenu() {
      this.$emit ("openMenu");
    }
  },
}
</script>

<style scoped lang="scss">
  .header {
    padding: 40rem 0 31rem;
    &__content {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
  }
</style>
