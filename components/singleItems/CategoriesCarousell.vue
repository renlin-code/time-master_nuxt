<template>
  <div class="carousell">
    <div class="main-content-wrapper">
      <h2 class="carousell__title timemaster-subtitle">
        Categories
      </h2>
    </div>
    <div class="carousell__viewport">
      <div class="carousell__wrapper">
        <CategoryCard class="carousell__category" />
        <CategoryCard class="carousell__category" />
        <CategoryCard class="carousell__category" />
        <CategoryCard class="carousell__category" />
        <CategoryCard class="carousell__category" />
        <CategoryCard class="carousell__category" />
      </div>
    </div>
  </div>
</template>

<script>
import CategoryCard from '../UIKit/CategoryCard.vue';

export default {
  name: "CategoriesCarousell",
  components: {CategoryCard}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .carousell {
    margin-bottom: 30rem;

    &__title {
      margin-bottom: 13rem;
      color: $gray;
    }
    &__viewport {
      width: 100%;
      overflow-x: scroll;
      overscroll-behavior-x: contain;
      scroll-snap-type: x proximity;
    }
    &__wrapper {
      display: flex;
      gap: 14rem;
      padding-bottom: 20rem;
    }
    &__category {
      min-width: 205rem;
      &:first-child {
        margin-left: 25rem;
      }
      &:last-child {
        margin-right: 25rem;
      }
    }
  }
</style>
