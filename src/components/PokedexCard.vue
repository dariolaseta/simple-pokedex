<template>
    <h3>Pokedex Card</h3>
</template>

<script>
import axios from 'axios';

export default {
    name: 'PokedexCard',

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

<style lang="scss" scoped>
    
</style>