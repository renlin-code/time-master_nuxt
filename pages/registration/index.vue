<template>
<section class="registration">
  <registration-figure class="registration__figure" />
  <div class="registration__lower-half">
    <h1 class="registration__title timemaster-title">
      Manage Your Time
    </h1>
    <h2 class="registration__subtitle timemaster-subtitle">
      Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet sint.
    </h2>
    <div class="registration__input">
      <input class="registration__input" type="text" placeholder="Write down your name" />
    </div>
    <ArrowButton class="registration__button" />
  </div>
</section>
</template>

<script>
import RegistrationFigure from '../../components/figures/figure-registration.vue';
import ArrowButton from '../../components/UIKit/ArrowButton.vue';

export default {
  name: "IndexPage",
  layout: "start",
  components: {RegistrationFigure, ArrowButton}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";
  .registration {
  @media only screen and (min-width: 650px) {
      max-width: 600rem;
      position: absolute;
      bottom: 0;

  }
    &__figure {
      padding-top: 50rem;
      display: flex;
      justify-content: center;
    }
    &__lower-half {
      min-height: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      background-color: #FFFFFF;
      box-shadow: inset 0 4rem 4rem $main-color;
      border-radius: 30rem 30rem 0 0;
      padding: 42rem 19rem 53rem;
    }
    &__title {
      padding-bottom: 26rem;
      text-align: center;
    }
    &__subtitle {
      color: $gray;
      text-align: center;
      padding: 0 15rem 54rem;
    }
    &__input {
      width: 100%;
      padding: 0 20rem;
      input {
        border: none;
        background: transparent;
        text-align: center;
        border-bottom: 1px solid rgba($gray, 0.7);
        width: 100%;
        padding: 6rem 0;
          &::placeholder {
          color: rgba($gray, 0.7);
        }
        &:focus {
          outline: none;
        }
      }
    }
    &__button {
      margin-top: 30rem;
    }
  }
</style>
