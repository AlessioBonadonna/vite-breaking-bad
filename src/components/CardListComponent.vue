<template>
    <SeachBarComponent @filterchar="getCharacters" />
    <div class="card-list-container">
        <CounterChar />
        <CardComponent :character="store.characterList" :loading="store.loading" />
    </div>
</template>

<script>
import axios from 'axios'
import CardComponent from './CardComponent.vue';
import SeachBarComponent from './SeachBarComponent.vue';
import CounterChar from './CounterChar.vue';
import { store } from '../store';




export default {

    components: {
        CardComponent,
        SeachBarComponent,
        CounterChar
    }, data() {
        return {
            store
        }
    },
    methods: {

        getCharacters(category) {
            //this.loading = true;
            let options = null
            if (category) {
                options = {

                    params: {
                        category: category
                    }

                }
            }


            axios.get(store.apiURL, options).then(
                (res) => {

                    store.characterList = [...res.data]
                    console.log(store.characterList)
                    store.loading = false;
                },

            )
                .catch((error) => {

                    console.log(error);
                })
        }
    },
    created() {
        //chiamata api ad inizio app
        this.getCharacters()
    }
}

</script>

<style lang="scss" scoped>

</style>