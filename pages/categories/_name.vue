<template>
  <section class="inner-category">
    <Page blur>
      <template #title>
        Work <categories class="inner-category__title-icon" />
      </template>
      <template #content>
        <div class="inner-category__undone-tasks">
          <TasksList />
        </div>
        <div class="inner-category__done-tasks">
          <TasksList />
        </div>
        <AddButton class="inner-category__button"
          @click.native="showModal = true"
        />
      </template>
    </Page>

    <InputModal
      v-if=showModal
      placeholder="Enter new task">

      <template #content>
        <div class="modal__params">
          <CalendarAccordion />
          <ImportantButton />
        </div>
        <OkButton class="modal__button" />
      </template>
    </InputModal>

  </section>
</template>

<script>
import Page from '../../components/Layout/Page.vue';
import InputModal from '../../components/Layout/InputModal.vue';
import categories from '../../components/icons/categories.vue';
import TasksList from '../../components/UIKit/TasksList.vue';
import AddButton from '../../components/UIKit/AddButton.vue';
import CalendarAccordion from '../../components/UIKit/CalendarAccordion.vue';
import ImportantButton from '../../components/UIKit/ImportantButton.vue';
import OkButton from '../../components/UIKit/OkButton.vue';

export default {
  name: 'IndexPage',
  components: {Page, InputModal, categories, TasksList, AddButton, CalendarAccordion, ImportantButton, OkButton},
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
  .inner-category {
    position: relative;
    &__title-icon::deep svg {
      width: 22rem;
      height: 22rem;
    }
    &__button {
      position: fixed;
      right: 25rem;
      bottom: 27rem;
    }
    &__undone-tasks {
      margin-bottom: 14rem;
    }
  }

  .modal {
    &__params {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 32rem;
      padding-bottom: 27rem;
    }
    &__button {
      position: fixed;
      right: 25rem;
      bottom: 27rem;
    }
  }
</style>
