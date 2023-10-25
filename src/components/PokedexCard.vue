<template>
    <div class="card text-center my-4 p-2">
        <span class="fs-2 text-capitalize">{{ pokemonInfo.name }}</span>
    </div>
</template>

<script>

export default {
    name: 'PokedexCard',

    props:{
        pokemonInfo: Object,
    },

    methods: {
        getPokemonInfo(){
        }
    },

    created() {
        this.getPokemonInfo();
    },
}
</script>

<style lang="scss" scoped>
    
</style>