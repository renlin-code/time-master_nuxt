<template>
  <section class="tasks-list">
    <div class="main-content-wrapper">
      <h2 class="tasks-list__title timemaster-subtitle">Today’s tasks</h2>
    </div>
    <ul class="tasks-list__list">
      <Task />
      <Task />
      <Task />
      <Task />
      <Task />
      <Task />
    </ul>
  </section>
</template>

<script>
import Task from './Task.vue';

export default {
  name: "TasksList",
  components: {Task}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .tasks-list {
    &__title {
      margin-bottom: 20rem;
      color: $gray;
    }
  }
</style>
