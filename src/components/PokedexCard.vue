<template>
    <div class="card text-center my-4 p-2">
        <h1 class="text-capitalize">{{ pokemonInfo.name }}</h1>

        <div class="fs-4 text-capitalize" v-for="(types, index) in pokemonData.types">
            <span>Type {{ index + 1 }}: {{ types.type.name }}</span>
        </div>

        <span class="fs-4 text-capitalize">Pokedex number: {{ pokemonData.id }}</span>

        <div class="fs-4 text-capitalize" v-for="(abilities, index) in pokemonData.abilities">
            <span v-if="!abilities.is_hidden">Ability {{ index + 1 }}: {{ abilities.ability.name }}</span>
            <span v-else>Hidden Ability: {{ abilities.ability.name }}</span>
        </div>

        <img v-if="pokemonData.sprites" :src="pokemonData.sprites.front_default" :alt="pokemonInfo.name + ' sprite'">
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'PokedexCard',

    props:{
        pokemonInfo: Object,
    },

    data() {
        return {
            pokemonData: [],
        }
    },

    methods: {
        getPokemonInfo(){
            axios.get(this.pokemonInfo.url)
            .then((response) =>{
                this.pokemonData = response.data;

                console.log(this.pokemonData)
            })
        }
    },

    created() {
        this.getPokemonInfo();
    },
}
</script>

<style lang="scss" scoped>
    
</style>