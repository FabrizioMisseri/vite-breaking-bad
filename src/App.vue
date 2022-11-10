<script>
import axios from "axios";
import { store } from "./store.js";
import appMain from './components/appMain.vue';
import headerLogo from "./components/headerLogo.vue";
import appLoad from "./components/appLoad.vue";

export default {
  name: "AppVue",

  components: {
    appMain,
    headerLogo,
    appLoad,
  },

  data() {
    return {
      store,
    }
  },

  created() {
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.arrayCharacters = resp.data;
      console.log("qui", this.store.arrayCharacters);
    });
    this.store.flag = !this.store.flag;
  },
}
</script>

<template>
  <div class="wrapper">
    <headerLogo />

    <div class="container">

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
  height: 100vh;
  display: flex;
  align-items: flex-end;
  position: relative;
}

.container {
  width: 70%;
  height: 70%;
  margin: 0 auto;
  background-color: white;
  padding: 1.5rem;
  overflow-y: auto;
}
</style>
