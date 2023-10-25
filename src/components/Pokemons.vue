<template>
    <div class="container justify-content-center">
        <div class="row">
            <div class="col-lg-4 col-md-6 col-sm-12" v-for="pokemon in pokedex">
                <PokedexCard :pokemonInfo = "pokemon" />
            </div>
        </div>
    </div>
</template>


<script>
import PokedexCard from './PokedexCard.vue';

import axios from 'axios';


export default {
name: 'Pokemons',

components:{
    PokedexCard
},

data() {
return {
    apiUrl: "https://pokeapi.co/api/v2/pokemon?limit=100000&offset=0",
    pokedex: [],
    pokemonUrl: [],
    }
},
methods: {
    getPokedexApi(){
    axios.get(this.apiUrl)
    .then((response)=> {
        this.pokedex = response.data.results;
        console.log(this.pokedex[0].url);

    })
    }
},
created() {
    this.getPokedexApi();
    },
}
</script>

<style lang="scss" scoped>
    
</style>