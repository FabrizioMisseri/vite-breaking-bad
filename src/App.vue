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
      apiUrl: "https://www.breakingbadapi.com/api/characters",
      queryUrlSaul: "?category=Better+Call+Saul",
      queryUrlBad: "?category=Breaking+Bad",
    }
  },

  created() {
    this.callAxios();
  },

  methods: {

    callAxios() {
      this.store.loaderFlag = false;

      if (this.store.selectSerie === "") {
        axios.get(this.apiUrl).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.loaderFlag = true;
        });

      } else if (this.store.selectSerie === "Better Call Saul") {
        axios.get(`${this.apiUrl}${this.queryUrlSaul}`).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.loaderFlag = true;
        });
      } else if (this.store.selectSerie === "Breaking Bad") {
        axios.get(`${this.apiUrl}${this.queryUrlBad}`).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.loaderFlag = true;
        });
      }
    },

  },
}
</script>

<template>
  <div class="wrapper">

    <div class="container">


      <headerApp @choice="callAxios()" />
      <appMain v-if="store.loaderFlag" />
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
}
</style>
