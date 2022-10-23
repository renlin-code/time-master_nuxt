<template>
  <section class="calendar">
    <Page blur>
      <template #title>
        Calendar
      </template>
      <template #content>
        <div class="main-content-wrapper">
          <Calendar class="calendar__calendar" />
        </div>

        <div class="calendar__undone-tasks">
          <TasksList />
        </div>
        <div class="calendar__done-tasks">
          <TasksList />
        </div>
        <AddButton class="calendar__button"
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
import Calendar from '../../components/UIKit/Calendar.vue';
import TasksList from '../../components/UIKit/TasksList.vue';
import AddButton from '../../components/UIKit/AddButton.vue';
import CategoriesAccordion from '../../components/UIKit/CategoriesAccordion.vue';
import ImportantButton from '../../components/UIKit/ImportantButton.vue';
import OkButton from '../../components/UIKit/OkButton.vue';

export default {
  name: 'IndexPage',
  components: {Page, InputModal, Calendar, TasksList, AddButton, CategoriesAccordion, ImportantButton, OkButton},
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
  .calendar {
    position: relative;
    &__button {
      position: fixed;
      right: 25rem;
      bottom: 27rem;
    }
    &__calendar {
      margin-bottom: 40rem;
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
