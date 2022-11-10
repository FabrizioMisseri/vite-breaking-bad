<script>
export default {
    name: "cardMain",

    props: {
        person: Object,
    },

    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="card">
        ciao
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;

.card {
    background-color: $primary-color;
    width: calc(100% / 5 - 20px);
    margin-bottom: 1rem;
    padding: .8rem;
    // debug
    color: white;
    height: 100px;
}
</style>