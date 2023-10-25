<template>
  <HeaderApp />
  <Pokemons />
  <FooterApp />
</template>

<script>
import HeaderApp from './components/HeaderApp.vue';
import Pokemons from './components/Pokemons.vue';
import FooterApp from './components/FooterApp.vue';

export default {
  name: 'App',

  components:{
    HeaderApp,
    Pokemons,
    FooterApp
  },
}
</script>

<style lang="scss">
  
</style>