<template>
    <div v-html="`found ${store.characterList.length} characters`" class="bg-dark text-white text-center"></div>
</template>

<script>
import { store } from '../store'
export default {
    name: 'CounterChar',
    data() {
        return {
            store
        }
    }
}
</script>

<style lang="scss" scoped>

</style>