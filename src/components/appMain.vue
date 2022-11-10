<script>
import cardMain from './cardMain.vue';

export default {
    name: "appMain",

    components: {
        cardMain,
    },

    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="box-header">
        <p>
            Found X characters
        </p>
    </div>

    <div class="box-cards d-flex justify-between">
        <cardMain />
        <cardMain />
        <cardMain />
        <cardMain />
        <cardMain />

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