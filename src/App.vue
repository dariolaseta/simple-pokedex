<template>
  <h1>test</h1>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      apiUrl: "https://pokeapi.co/api/v2/pokemon?limit=100000&offset=0",
      pokedex: []
    }
  },
  methods: {
    getPokedexApi(){
      axios.get(this.apiUrl)
      .then((response)=> {
        console.log(response.data);
      })
    }
  },
  mounted() {
    this.getPokedexApi();
  },
}
</script>

<style lang="scss">
  
</style>