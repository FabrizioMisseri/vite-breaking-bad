<script>
export default {
    name: "cardMain",

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
    // debug
    color: white;
    height: 100px;
}
</style>