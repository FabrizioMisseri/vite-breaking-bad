<script>
export default {
    name: "header App"
}
</script>

<template>
    <header>

        <div class="logo">
            <img src="../assets/img/Breaking_Bad_logo.svg.png" alt="">
        </div>

        <div class="category-selector">
            <select name="" id="">

                <option value="">empty</option>
                <option value="">BB</option>
                <option value="">BCS</option>

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