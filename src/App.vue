<template>
  <nav>
    <HeaderComponent />

  </nav>
  <main>
    <div class="container mt-5">
      <!-- <SeachBarComponent /> -->
      <CardListComponent />



    </div>

  </main>
</template>

<script>


import CardListComponent from './components/CardListComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import SeachBarComponent from './components/SeachBarComponent.vue';

export default {
  components: {
    HeaderComponent,
    SeachBarComponent,
    CardListComponent,

  },
}


</script>

<style lang="scss" scoped>

</style>