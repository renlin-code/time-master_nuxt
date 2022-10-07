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
        <AddButton class="home__button" />
      </template>
    </Page>
  </section>
</template>

<script>
import Page from '../components/Layout/Page.vue';
import CategoriesCarousell from '../components/singleItems/CategoriesCarousell.vue';
import TasksList from '../components/UIKit/TasksList.vue';
import AddButton from '../components/UIKit/AddButton.vue';

export default {
  name: 'IndexPage',
  components: {Page, CategoriesCarousell, TasksList, AddButton}
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
</style>
