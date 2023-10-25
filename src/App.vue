<template>
  <HeaderApp />
  <Pokemons />
</template>

<script>
import HeaderApp from './components/HeaderApp.vue';
import Pokemons from './components/Pokemons.vue';

export default {
  name: 'App',

  components:{
    HeaderApp,
    Pokemons
  },
}
</script>

<style lang="scss">
  
</style>