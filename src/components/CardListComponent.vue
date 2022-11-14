<template>
    <div class="card-list-container">
        <div v-html="`found ${characterList.length} characters`" class="bg-dark text-white text-center"></div>
        <CardComponent :character="characterList" />
    </div>
</template>

<script>
import axios from 'axios'
import CardComponent from './CardComponent.vue';


export default {

    components: {
        CardComponent,
    }, data() {
        return {
            apiURL: 'https://www.breakingbadapi.com/api/characters',
            characterList: [],
            loading: false
        }
    },
    methods: {

        getCharacters() {
            // this.loading = true;
            axios.get(this.apiURL).then(
                (res) => {

                    this.characterList = [...res.data]
                    console.log(this.characterList)
                    // this.loading = false;
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