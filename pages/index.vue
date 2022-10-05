<template>
  <section class="home">
    <Page blur>
      <template #title>
        Hello, Rene!
      </template>
      <template #content>
        <CategoriesCarousell />

        <Task />
      </template>
    </Page>
  </section>
</template>

<script>
import Page from '../components/Layout/Page.vue';
import CategoriesCarousell from '../components/singleItems/CategoriesCarousell.vue';
import Task from '../components/UIKit/Task.vue';

export default {
  name: 'IndexPage',
  components: {Page, CategoriesCarousell, Task}
}
</script>
