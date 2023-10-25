<template>
    <div class="container justify-content-center">
        <div class="row">
            <div class="col-lg-4 col-md-6 col-sm-12 my_hover_effect" v-for="(pokemon, index) in pokedex" :key="pokemon.name">
                <PokedexCard :pokemonInfo = "{
                    name: pokemon.name,
                    url: `https://pokeapi.co/api/v2/pokemon/${index + 1}/`
                }" />
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
        apiUrl: "https://pokeapi.co/api/v2/pokemon?limit=20&offset=0",
        pokedex: [],
        pokemonUrl: [],
    }
},
methods: {
    getPokedexApi(){
    axios.get(this.apiUrl)
    .then((response)=> {
        this.pokedex = response.data.results;

        this.pokedex.forEach((pokemon, index) =>{
            pokemon.url = `https://pokeapi.co/api/v2/pokemon/${index + 1}/`;
        })

    })
    }
},
created() {
    this.getPokedexApi();
    },
}
</script>

<style lang="scss" scoped>
    div.my_hover_effect{
        transition: all .3s ease-in-out;
        z-index: 0;
    }

    div.my_hover_effect:hover{
        cursor: pointer;
        transform: scale(1.3);
        z-index: 1;
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
    }
</style>