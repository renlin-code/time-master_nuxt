<template>
  <li class="task">
    <div class="task__wrapper">
      <div class="task__default">
        <span class="task__default-icon">
          <taskCircle />
          <flag
            v-if=false
          />
        </span>
        <p class="task__default-text">
          Getting Started With Gnome Mines. Gnome Mines is a virtual world full
        </p>
      </div>

      <div class="task__delete">
        <div class="task__delete-left">
          <trash />
          The task was deleted
        </div>
        <button class="task__delete-undo">Undo</button>
      </div>

    </div>
  </li>
</template>

<script>
import taskCircle from '../icons/taskCircle.vue';
import flag from '../icons/flag.vue';
import trash from '../icons/trash.vue';

export default {
  name: "Task",
  components: {taskCircle, flag, trash}

}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .task {
    width: 100%;
    padding-bottom: 10rem;
    overflow-x: hidden;
    &__wrapper {
      display: flex;
      transition: transform 300ms ease-in-out;
    }
    &__default {
      min-width: 100%;
      background-color: #FFFFFF;
      padding: 8rem 20rem;
      display: grid;
      grid-template-columns: 20rem auto;
      column-gap: 12rem;
      align-items: center;
      border-radius: 20rem;
      box-shadow: 0px 4px 4px rgba( $black, 0.25);
      &-text {
        transition: all 360ms ease-in-out;
      }
    }
    &__delete {
      min-width: 100%;
      display: flex;
      align-items: center;
      justify-content: space-between;
      &-left {
        display: grid;
        grid-template-columns: 20rem auto;
        column-gap: 16rem;
        align-items: center;
        color: $gray;
      }
      &-undo {
        width: 63rem;
        height: 32rem;
        border: 2rem solid rgba( $gray, 0.5);
        border-radius: 30rem;
        padding: 7rem 16rem;
        color: $gray;
        font-size: 12rem;
        line-height: 18rem;
        box-shadow: 0px -1px 4px rgba($black, 0.25);
      }
    }


    &--deleted {
      .task__wrapper {
        transform: translateX(-100%);
      }
    }
    &--done {
      .task__default-text {
        text-decoration-line: line-through;
        opacity: 0.6;
        color: $gray;
      }
    }
    &--old {
      .task__default-text {
        color: #DE2424;
      }
    }
  }
</style>
