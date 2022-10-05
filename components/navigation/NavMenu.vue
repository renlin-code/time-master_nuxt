<template>
<nav class="menu">
  <div class="menu__head head-layout">
    <nuxt-link to="/">
      <logo class="menu__logo" width="184rem" height="25rem" />
    </nuxt-link>
  </div>
  <div class="menu__body body-layout">
    <ul class="menu__list">
      <li>
        <nuxt-link to="/">
          <home />
          Home
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/categories">
          <categories />
          Categories
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/calendar">
          <calendar />
          Calendar
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/settings">
          <gear />
          Settings
        </nuxt-link>
      </li>
    </ul>
    <figure-menu class="menu__figure" />
  </div>
</nav>
</template>

<script>
import logo from '../icons/logo.vue';
import home from '../icons/home.vue';
import categories from '../icons/categories.vue';
import calendar from '../icons/calendar.vue';
import gear from '../icons/gear.vue';
import FigureMenu from '../figures/figure-menu.vue';

export default {
  name: "NavMenu",
  components: {logo, home, categories, calendar, gear, FigureMenu}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";

  .menu {
    &__logo {
      padding: 58rem 0 0 25rem;
    }
    &__list {
      padding: 188rem 0 0 23rem;
      li a {
        display: grid;
        grid-template-columns: 23rem auto;
        column-gap: 12rem;
        color: $gray;
        font-size: 24px;
        line-height: 36px;
        font-weight: 500;
        margin-bottom: 5rem;
        text-transform: uppercase;
        align-items: center;
      }
    }
    &__figure {
      margin-top: 134rem;
      padding-left: 16rem;
    }
  }
</style>
