<template>
  <nav>
    <HeaderComponent />

  </nav>
  <main>
    <div class="container mt-5">
      <SeachBarComponent />
      <CardListComponent />
      <CardComponent :character="characterList" />
    </div>

  </main>
</template>

<script>
import axios from 'axios';
import CardComponent from './components/CardComponent.vue';
import CardListComponent from './components/CardListComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import SeachBarComponent from './components/SeachBarComponent.vue';

export default {
  components: {
    HeaderComponent,
    SeachBarComponent,
    CardListComponent,
    CardComponent
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