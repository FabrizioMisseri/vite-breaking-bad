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
        <div class="box-img">
            <img :src="person.img" alt="">
        </div>

        <div class="box-txt">
            <p class="name">
                {{ person.name }}
            </p>

            <p class="series">
                {{ person.category }}
            </p>

            <p class="life-status">
                {{ person.status }}
            </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;

.card {
    background-color: $primary-color;
    width: calc(100% / 5 - 20px);
    margin-bottom: 1rem;
    padding: .8rem;

    .box-txt {
        .name {
            color: white;
            font-weight: 600;
        }

        .series,
        .life-status {
            color: $gray-text-color;
            font-size: .85rem;
            font-size: 500;
        }

        p {
            margin-top: .5rem;
        }
    }
}
</style>