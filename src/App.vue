<template>
  <HeaderApp />
  <PokedexCard />
</template>

<script>
import HeaderApp from './components/HeaderApp.vue';
import PokedexCard from './components/PokedexCard.vue';

export default {
  name: 'App',

  components:{
    HeaderApp,
    PokedexCard
  },
}
</script>

<style lang="scss">
  
</style>