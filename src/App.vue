<script>
import appMain from './components/appMain.vue';

export default {
  name: "AppVue",

  components: {
    appMain,
  },

  data() {
    return {

    }
  },
}
</script>

<template>
  <div class="wrapper">
    <div class="container">

      <appMain />

    </div>
  </div>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables.scss" as *;

body {
  background-color: $primary-color;
}

.wrapper {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: flex-end;
}

.container {
  width: 70%;
  height: 70%;
  margin: 0 auto;
  background-color: white;
  padding: 1.5rem
}
</style>
