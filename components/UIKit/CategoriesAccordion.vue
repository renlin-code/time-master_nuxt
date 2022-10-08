<template>
  <div class="categories-accordion"
    :class="{'categories-accordion--open' : open}"
  >
    <div class="categories-accordion__head"
      @click="open = !open"
    >
      <categories class="categories-accordion__head-icon" />
      <span class="timemaster-subtitle">Categories</span>
    </div>
    <ul class="categories-accordion__body">
      <li class="categories-accordion__body-item"
        :class="{'selected' : selected===1}"
        @click="selected=1"
      >
        <category-circle color="#EF5DA8" class="categories-accordion__body-icon" />
        <span>Work</span>
      </li>
      <li class="categories-accordion__body-item"
        :class="{'selected' : selected===2}"
        @click="selected=2"
      >
        <category-circle color="#7879F1" class="categories-accordion__body-icon" />
        <span>Finance</span>
      </li>
      <li class="categories-accordion__body-item"
        :class="{'selected' : selected===3}"
        @click="selected=3"
      >
        <category-circle color="#2ED535" class="categories-accordion__body-icon" />
        <span>Study</span>
      </li>
      <li class="categories-accordion__body-item"
        :class="{'selected' : selected===4}"
        @click="selected=4"
      >
        <category-circle color="#7879F1" class="categories-accordion__body-icon" />
        <span>Finance</span>
      </li>
      <li class="categories-accordion__body-item"
        :class="{'selected' : selected===5}"
        @click="selected=5"
      >
        <category-circle color="#7879F1" class="categories-accordion__body-icon" />
        <span>Finance</span>
      </li>


    </ul>
  </div>
</template>

<script>
import categories from '../icons/categories.vue';
import categoryCircle from '../icons/categoryCircle.vue';

export default {
  name: "CategoriesAccordion",
  components: {categories, categoryCircle},
  data: () => ({
    selected: 1,
    open: false
  }),
  // watch: {
  //   selected() {
  //     this.open = false;
  //   }
  // }
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .categories-accordion {
    width: 300rem;
    margin: 0 auto;
    overflow: hidden;
    background: #ffffff;
    border-radius: 30rem;
    box-shadow: 0px 4px 4px rgba($black, 0.25);
    &__head {
      width: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10rem;
      padding: 20rem 0;

      span {
        color: $gray;
      }
      &-icon {
        display: grid;
        place-content: center;
      }
    }
    &__body {
      &-item {
        width: 100%;
        height: 0;
        overflow: hidden;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        gap: 10rem;
        padding-left: 93rem;
        transition: height 360ms ease-in-out;
        span {
          color: $black;
          max-width: 130rem;
          max-height: 24rem;
          overflow: hidden;
        }
        &-icon {
          display: grid;
          place-content: center;
        }
        &.selected {
          background: #EEF6FC;
        }
      }
    }
    &--open {
      .categories-accordion {
        &__body {
          padding-bottom: 10rem;
          &-item {
            height: 34rem;
          }
        }
      }
    }
  }
</style>
