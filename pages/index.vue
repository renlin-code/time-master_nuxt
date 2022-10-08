<template>
  <section class="home">
    <Page blur>
      <template #title>
        Hello, Rene!
      </template>
      <template #content>
        <CategoriesCarousell />
        <div class="home__todays-tasks">
          <TasksList />
        </div>
        <div class="home__done-tasks">
          <TasksList />
        </div>
        <AddButton class="home__button"
          @click.native="showModal = true"
        />
      </template>
    </Page>

    <InputModal
      v-if=showModal
      placeholder="Enter new task">

      <template #content>
        <div class="modal__params">
          <CategoriesAccordion />
          <CalendarAccordion />
          <ImportantButton />
        </div>
        <OkButton class="modal__button" />
      </template>
    </InputModal>

  </section>
</template>

<script>
import Page from '../components/Layout/Page.vue';
import InputModal from '../components/Layout/InputModal.vue';
import CategoriesCarousell from '../components/singleItems/CategoriesCarousell.vue';
import TasksList from '../components/UIKit/TasksList.vue';
import AddButton from '../components/UIKit/AddButton.vue';
import CategoriesAccordion from '../components/UIKit/CategoriesAccordion.vue';
import CalendarAccordion from '../components/UIKit/CalendarAccordion.vue';
import ImportantButton from '../components/UIKit/ImportantButton.vue';
import OkButton from '../components/UIKit/OkButton.vue';

export default {
  name: 'IndexPage',
  components: {Page, InputModal, CategoriesCarousell, TasksList, AddButton, CategoriesAccordion, CalendarAccordion, ImportantButton, OkButton},
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
  .home {
    position: relative;
    &__button {
      position: fixed;
      right: 25rem;
      bottom: 27rem;
    }
    &__todays-tasks {
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
