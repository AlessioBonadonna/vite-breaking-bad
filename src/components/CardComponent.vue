<template>
    <div class="container">
        <div class="row carta  ">
            <div class="col-2 p-3  m-3 fix-card  text-center" v-for="(item, index) in character " :key="item.char_id">
                <img :src="item.img" :alt="item.name">
                <h3 class="mt-2 text-white">{{ item.name }}</h3>
                <h5 class="text-secondary">{{ item.category }}</h5>
                <p class="text-secondary">{{ item.status }}</p>
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: [
        'character'
    ],
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

.fix-card {
    margin: 0 10px;
    background-color: $bg-color;
}
</style>