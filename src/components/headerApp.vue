<script>
import { store } from '../store.js';

export default {
    name: "header App",

    data() {
        return {
            store,
            categories: ["Breaking Bad", "Better Call Saul"],
        }
    }
}
</script>

<template>
    <header>

        <div class="logo">
            <img src="../assets/img/Breaking_Bad_logo.svg.png" alt="">
        </div>

        <div class="category-selector">
            <select v-model="store.selectSerie">
                <option value="">empty</option>
                <option v-for="(category, index) in categories" :value="category" :key="index">{{ category }}</option>
            </select>
        </div>

    </header>

</template>

<style lang="scss" scoped>
header {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;

    .logo {
        img {
            max-height: 24vh;
        }
    }

    .category-selector {
        select {
            width: 400px;
            padding: .7rem;
            font-size: 1.2rem;
        }
    }
}
</style>