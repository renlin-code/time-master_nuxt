<template>
  <div class="add-button"
    :class="{'add-button--animated' : animated}"
  >
    <button class="add-button__button">
      <div class="add-button__button-cross">
        <div class="add-button__button-cross-line"></div>
        <div class="add-button__button-cross-line"></div>
      </div>
    </button>

    <div class="add-button__cta-wrapper">
      <div class="add-button__cta-inner">
        <span class="timemaster-subtitle">Add new tasks</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AddButton",
  props: {
    animated: {
      type: Boolean,
      default: false
    }
  }
}

</script>
<style scoped lang="scss">
  @import "../../static/scss/_vars.scss";

  .add-button {
    position: relative;
    cursor: pointer;
    width: 269rem;
    height: 80rem;
    border-radius: 35rem;
    z-index: 0;
    &__button {
      position: absolute;
      right: 0;
      width: 78rem;
      height: 78rem;
      border-radius: 50%;
      background-color: $main-color;
      display: grid;
      place-content: center;
      z-index: 1;
      transform-origin: center;
      box-shadow: 0px 2px 4px rgba($black, 0.25);
      &-cross {
        width: 28rem;
        height: 28rem;
        position: relative;
        &-line {
          background-color: #ffffff;
          position: absolute;
          border-radius: 3rem;
          box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
          &:first-child {
            top: 12.5rem;
            left: 0;
            width: 28rem;
            height: 3rem;
          }
          &:last-child {
            top: 0;
            left: 12.5rem;
            width: 3rem;
            height: 28rem;
          }
        }

      }
    }
    &__cta {
      &-wrapper {
        position: absolute;
        overflow: hidden;
        top: 5rem;
        right: 20rem;
        width: 255rem;
        height: 68rem;
        z-index: -1;
      }
      &-inner {
        position: absolute;
        top: 0;
        right: 0;
        width: 255rem;
        height: 68rem;
        padding: 19rem 92rem 19rem 35rem;
        background-color: #ffffff;
        border-radius: 30rem;
        transform: translateX(120%);
        box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
        span {
          color: $gray;
        }
      }
    }

    &--animated {
      .add-button {
        &__button {
          animation-name: button;
          animation-duration: 4s;
          animation-iteration-count: infinite;
        }
        &__cta-inner {
          animation-name: cta;
          animation-duration: 4s;
          animation-iteration-count: infinite;
        }
      }
    }

    @keyframes button {
      5% {
        transform: rotate(30deg);
      }
      15% {
        transform: rotate(-30deg);
      }
      20% {
        transform: rotate(0deg);
      }
    }
    @keyframes cta {
      10%, 50% {
        transform: translateX(0);
      }
      60% {
        transform: translateX(120%);
      }
    }

  }
</style>
