<template>
    <div class="screen">
      <div class="front-layer background-front wrapper"
      :class="{'front-layer--open' : frontOpen}"
      >
        <header class="head-layout">
          <HeaderDefault
            @openMenu="frontOpen=true"
          />
        </header>
        <main class="body-layout">
          <Nuxt />
        </main>
        <div class="front-layer__cover-layer"
          v-if="frontOpen"
          @click="frontOpen=false"
        ></div>
      </div>

      <div class="back-layer wrapper"
      >
        <NavMenu
          @click.native="frontOpen=false"
        />
      </div>
    </div>
</template>

<script>
import HeaderDefault from '../components/headers/HeaderDefault.vue';
import NavMenu from '../components/navigation/NavMenu.vue';


export default {
  components: {HeaderDefault, NavMenu},
  data: () => ({
    frontOpen: false
  })
}
</script>

<style scoped lang="scss">
@import "../static/scss/_vars.scss";

.background-front {
  background-image: url("../static/img/background1.png");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.front-layer {
  z-index: 2;
  background-color: #FFFFFF;
  transition: all 360ms ease-in-out;
  box-shadow: 0px -5px 4px rgba($black, 0.25), -6px 4px 4px rgba($black, 0.25);

  &__cover-layer {
    width: 100%;
    height: 100%;
    position: fixed;
    cursor: pointer;
    border-radius: 35rem;
    z-index: 2;
  }

  &--open {
    transform: translateX(253rem) scale(0.93);
    border-radius: 35rem;
  }
}

.back-layer {
  background-image: url("../static/img/background-menu.png");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;

}
</style>
