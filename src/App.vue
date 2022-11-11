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
    }
  },

  created() {
    this.callAxios();
  },

  methods: {
    greet() {
      alert("ciao");
    },

    callAxios() {
      if (this.store.selectSerie === "") {
        axios.get(this.apiUrl).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.flag = !this.store.flag;
        });

      } else if (this.store.selectSerie === "Better Call Saul") {
        axios.get(`${this.apiUrl}?category=Better+Call+Saul`).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.flag = !this.store.flag;
        });
      } else {
        axios.get(`${this.apiUrl}?category=Breaking+Bad`).then((resp) => {
          this.store.arrayCharacters = resp.data;
          this.store.flag = !this.store.flag;
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
}
</style>
