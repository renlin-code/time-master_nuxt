<template>
  <transition name="scale">
    <li class="task"
      :class="{
        'task--done': done,
        'task--deleted': deleted
        }"
    >
      <div class="task__wrapper">
        <div class="task__default">
          <span class="task__default-icon"
            @click="done = !done"
          >
            <flag v-if=important :color=color />
            <taskCircle v-else :color=color />
          </span>
          <p class="task__default-text"
            @click="deleted = true"
          >{{ text }}</p>
        </div>

        <div class="task__delete">
          <div class="task__delete-left">
            <trash />
            The task was deleted
          </div>
          <button class="task__delete-undo"
            @click="deleted = false"
          >Undo</button>
        </div>

      </div>
    </li>
  </transition>
</template>

<script>
import taskCircle from '../icons/taskCircle.vue';
import flag from '../icons/flag.vue';
import trash from '../icons/trash.vue';

export default {
  name: "Task",
  components: {taskCircle, flag, trash},
  props: {
    important: {
      type: Boolean,
      default: false
    },
    color: {
      type: String,
      default: "#777777"
    },
    text: {
      type: String,
      default: "Put a text inside of me using prop 'text'"
    }
  },
  data: () => ({
    done: false,
    deleted: false
  })

}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .task {
    width: 100%;
    padding: 0 25rem 15rem;
    overflow-x: hidden;
    &__wrapper {
      display: flex;
      gap: 40rem;
      transition: transform 360ms ease-in-out;
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
        box-shadow: 0px 1px 4px rgba($black, 0.25);
      }
    }

    &--done {
      .task__default-text {
        text-decoration-line: line-through;
        opacity: 0.6;
        color: $gray;
      }
    }

    &--deleted {
      .task__wrapper {
        transform: translateX(calc(-100% - 40rem));
      }
    }

    &--old {
      .task__default-text {
        color: #DE2424;
      }
    }
  }
</style>
