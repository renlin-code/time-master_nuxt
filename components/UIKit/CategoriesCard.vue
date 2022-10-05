<template>
  <div class="categories-card">
    <div v-if="extended" class="categories-card__top">
      <categories color="#4E9DA1" />
      <edit />
    </div>
    <h2 class="categories-card__title timemaster-subtitle">Work</h2>
    <span class="categories-card__tasks timemaster-caption">10 tasks</span>
    <div class="categories-card__progress">
      <div class="categories-card__progress-inner"></div>
    </div>
  </div>
</template>

<script>
import categories from '../icons/categories.vue';
import edit from '../icons/edit.vue';

export default {
  name: "CategoriesCard",
  components: {categories, edit},
  props: {
    extended: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .categories-card {
    background-color: #FFFFFF;
    padding: 15rem 20rem 21rem 20rem;
    border-radius: 20rem;
    box-shadow: 0px 4px 4px rgba($black, 0.25);
    &__top {
      display: flex;
      justify-content: space-between;
      margin-bottom: 7rem;
    }
    &__title {
      margin-bottom: 2rem;
    }
    &__tasks {
      display: inline-block;
      color: $gray;
      margin-bottom: 18rem;
    }
    &__progress {
        position: relative;
        filter: drop-shadow(0px 2px 2px rgba($black, 0.25));
        width: 100%;
        height: 10rem;
        border-radius: 20rem;
        background-color: $white;
        overflow: hidden;
        &-inner {
          position: absolute;
          left: 0;
          height: 100%;
          width: 25%;
          background-color: #4E9DA1;
          border-radius: 20rem;
          box-shadow: 1px 0px 2px rgba($black, 0.25);
        }
    }
  }
</style>
