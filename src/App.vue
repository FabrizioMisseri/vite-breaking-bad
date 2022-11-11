<script>
import axios from "axios";
import { store } from "./store.js";
import appMain from './components/appMain.vue';
import headerApp from "./components/headerApp.vue";
import appLoad from "./components/appLoad.vue";

export default {
  name: "AppVue",

  components: {
    appMain,
    headerApp,
    appLoad,
  },

  data() {
    return {
      store,
    }
  },

  created() {
    setTimeout(() => {

      axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
        this.store.arrayCharacters = resp.data;
        console.log("qui", this.store.arrayCharacters);
      });
      this.store.flag = !this.store.flag;

    }, 1000);

  },
}
</script>

<template>
  <div class="wrapper">

    <div class="container">

      <headerApp />
      <appMain v-if="store.flag" />
      <appLoad v-else />


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
  padding: 1rem;
}

.container {
  width: 70%;
  height: 70%;
  margin: 0 auto;
  padding: 1.5rem;
}
</style>
