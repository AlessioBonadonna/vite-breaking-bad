<template>
  <nav>
    <HeaderComponent />

  </nav>
  <main>
    <div class="container mt-5">
      <SeachBarComponent />
      <CardListComponent />
      <CardComponent />
    </div>

  </main>
</template>

<script>
import CardComponent from './components/CardComponent.vue';
import CardListComponent from './components/CardListComponent.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import SeachBarComponent from './components/SeachBarComponent.vue';

export default {
  components: { HeaderComponent, SeachBarComponent, CardListComponent, CardComponent }
}
</script>

<style lang="scss" scoped>

</style>