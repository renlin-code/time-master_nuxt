<template>
  <div class="categories-accordion">
    <div class="categories-accordion__head">
      <categories />
      <span>Categories</span>
    </div>
    <ul class="categories-accordion__body">
      <li class="categories-accordion__body-item">
        <category-circle />
        <span>Work</span>
      </li>
    </ul>
  </div>
</template>

<script>
import categories from '../icons/categories.vue';
import categoryCircle from '../icons/categoryCircle.vue';

export default {
  name: "CategoriesAccordion",
  components: {categories, categoryCircle}
}
</script>

<style scoped lang="scss">
  .categories-accordion {
    background: #ffffff;
  }
</style>
