<template>
  <section class="page">
    <div class="page__background-fig"
      :class="{'page__background-fig--blur' : blur}"></div>

    <div class="main-content-wrapper">
      <h1 class="page__title timemaster-title">
        <slot name="title"></slot>
      </h1>
    </div>
    <div class="page__content">
      <slot name="content"></slot>
    </div>
  </section>
</template>

<script>
export default {
  name: "Page",
  props: {
    blur: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
  .page {
    position: relative;

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
      &--blur {
        filter: blur(25rem);
      }
    }
    &__title {
      display: flex;
      align-items: center;
      gap: 10rem;
    }
    &__content {
      padding-top: 34rem;
      height: calc(100vh - 155rem);
      overflow: scroll;
    }
  }
</style>
