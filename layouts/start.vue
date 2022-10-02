<template>
    <div class="screen">
      <div class="background-front">
        <header class="head-layout">
          <logo width="288rem" height="40rem" class="logo" />
        </header>

        <main class="body-layout">
          <Nuxt />
        </main>
      </div>
    </div>
</template>

<script>
import logo from '../components/icons/logo.vue';

export default {
  name: "start",
  components: {logo}
}
</script>

<style scoped lang="scss">
.background-front {
  background-image: url("../static/img/background1.png");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.logo {
  display: flex;
  justify-content: center;
  padding-top: 47rem;
}
</style>
