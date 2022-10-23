<template>
  <button class="add-category">
    <div class="add-category__cross">
      <div class="add-category__cross-line"></div>
      <div class="add-category__cross-line"></div>
    </div>
  </button>
</template>

<style scoped lang="scss">
  @import "../../static/scss/_vars.scss";

  .add-category {
    width: 100%;
    height: 100%;
    border-radius: 20rem;
    background-color: #ffffff;
    box-shadow: 0px 4px 4px rgba($black, 0.25);
    display: grid;
    place-content: center;
    &__cross {
      width: 44rem;
      height: 44rem;
      position: relative;
      &-line {
        background-color: #18191A;
        position: absolute;
        border-radius: 3rem;
        &:first-child {
          top: 22rem;
          left: 0;
          width: 100%;
          height: 2rem;
        }
        &:last-child {
          top: 0;
          left: 22rem;
          width: 2rem;
          height: 100%;
        }
      }
    }
  }
</style>
