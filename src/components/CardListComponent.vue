<template>
    <SeachBarComponent @filterchar="getCharacters" />
    <div class="card-list-container">

        <div v-html="`found ${characterList.length} characters`" class="bg-dark text-white text-center"></div>
        <CardComponent :character="characterList" :loading="loading" />
    </div>
</template>

<script>
import axios from 'axios'
import CardComponent from './CardComponent.vue';
import SeachBarComponent from './SeachBarComponent.vue';



export default {

    components: {
        CardComponent,
        SeachBarComponent
    }, data() {
        return {
            apiURL: 'https://www.breakingbadapi.com/api/characters',
            characterList: [],
            loading: false
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


            axios.get(this.apiURL, options).then(
                (res) => {

                    this.characterList = [...res.data]
                    console.log(this.characterList)
                    this.loading = false;
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