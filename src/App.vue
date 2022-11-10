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
  <appMain />
</template>

<style lang="scss">
@use "./general.scss" as *;
</style>
