<template>
  <section class="categories">
    <Page blur>
      <template #title>
        My categories
      </template>
      <template #content>
        <div class="categories__wrapper main-content-wrapper">
        <CategoryCard extended />
        <CategoryCard extended />
        <CategoryCard extended />
        <AddCategory
          @click.native="showModal = true"
        />
        </div>
      </template>
    </Page>

    <InputModal
      v-if=showModal
      placeholder="Add new category">

      <template #content>
        <div class="modal__circles-wrapper">
          <category-circle selected extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
          <category-circle extended />
        </div>
        <OkButton class="modal__button" />
      </template>
    </InputModal>

  </section>
</template>

<script>
import Page from '../../components/Layout/Page.vue';
import InputModal from '../../components/Layout/InputModal.vue';

import CategoryCard from '../../components/UIKit/CategoryCard.vue';
import AddCategory from '../../components/UIKit/AddCategory.vue';
import categoryCircle from '../../components/icons/categoryCircle.vue';
import OkButton from '../../components/UIKit/OkButton.vue';

export default {
  name: 'IndexPage',
  components: {Page, InputModal, CategoryCard, AddCategory, categoryCircle, OkButton},
  data: () => ({
    showModal: false
  }),
  mounted() {
    this.$nuxt.$on('closeModal', () => {
      this.showModal = false;
    })
  }
}
</script>

<style scoped lang="scss">
  .categories {
    &__wrapper {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 25rem;
    }
  }

  .modal {
    &__circles-wrapper {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      row-gap: 14rem;
      column-gap: 17rem;
      padding: 0 80rem;
    }
    &__button {
      position: fixed;
      right: 25rem;
      bottom: 27rem;
    }
  }
</style>
