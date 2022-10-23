<template>
  <section class="settings">
    <Page blur>
      <template #title>
        Settings
      </template>
      <template #content>
        <div class="settings__wrapper main-content-wrapper">
          <h2 class="settings__title timemaster-subtitle">Automatic task removal after</h2>
        </div>
      </template>
    </Page>
  </section>
</template>

<script>
import Page from '../../components/Layout/Page.vue';

export default {
  name: 'IndexPage',
  components: {Page}
}
</script>

<style scoped lang="scss">
@import "../../static/scss/_vars.scss";
  .settings {
    &__title {
      color: $gray;
    }
  }
</style>
