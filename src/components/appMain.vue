<script>
import { store } from "../store.js";
import cardMain from './cardMain.vue';

export default {
    name: "appMain",

    components: {
        cardMain,
    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="box-header">
        <p>
            Found {{ store.arrayCharacters.length }} characters
        </p>
    </div>

    <div class="box-cards d-flex justify-between">

        <cardMain v-for="(character, index) in store.arrayCharacters" :key="index" :person="character" />

    </div>

</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;

.box-header {
    background-color: $secondary-color;
    color: white;
    padding: .8rem;
    margin: 0 auto 2rem;
    width: 90%;
}

.box-cards {
    width: 85%;
    margin: 0 auto;
}
</style>