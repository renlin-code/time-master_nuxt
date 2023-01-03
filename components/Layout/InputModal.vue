<template>
    <transition name="fade">
      <section class="input-modal">
        <div class="input-modal__background-fig"></div>

        <div class="main-content-wrapper">
          <textarea class="input-modal__input timemaster-title"
            type="text"
            :placeholder="placeholder"
          ></textarea>
          <close class="input-modal__close"
            @click.native="$nuxt.$emit('closeModal')"
          />
        </div>
        <div class="input-modal__content">
          <slot name="content"></slot>
        </div>
      </section>
    </transition>
</template>

<script>
import close from '../icons/close.vue';

export default {
  name: "input-modal",
  components: {close},
  props: {
    placeholder: {
      type: String,
      default: "Default placeholder"
    }
  }
}
</script>
<style scoped lang="scss">
  @import "../../static/scss/_vars.scss";

  .input-modal {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 3;
    width: 100%;
    height: 100vh;
    background-color: #ffffff;
    background-image: url("../../static/img/background1.png");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;

    &__background-fig {
      position: absolute;
      width: 355rem;
      height: 355rem;
      left: 37rem;
      top: 50%;
      transform: translateY(-25%);
      z-index: -1;
      background-image: url("../../static/img/background-figure.png");
      background-position: center;
      background-size: contain;
      background-repeat: no-repeat;
      filter: blur(25rem);
    }
    &__input {
      border: none;
      background: transparent;
      color: $gray;
      margin: 186rem 0 15rem;
      width: 100%;
      &::placeholder {
        color: rgba( $gray, 0.5);
      }
      &:focus {
        outline: none;
      }
    }
    &__close {
      position: absolute;
      top: 43rem;
      right: 25rem;
    }
    &__content {
      padding-top: 74rem;
      height: calc(100vh - 313rem);
      overflow: scroll;
    }
  }
</style>
