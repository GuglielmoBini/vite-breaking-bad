<script>
import axios from 'axios'
import PokemonCard from './PokemonCard.vue'
export default {
    name: 'PokemonList',
    components: { PokemonCard },
    data() {
        return {
            pokemons: []
        }
    },
    created() {
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=8').then(res => {
            this.pokemons = res.data.docs
        })
    }
}
</script>

<template>
    <section id="pokemon" class="container text-center">
        <div class="row justify-content-center">
            <pokemon-card v-for="pokemon in pokemons" :key="pokemon._id" :name="pokemon.name" :image="pokemon.imageUrl"
                :number="pokemon.number" :type1="pokemon.type1" :type2="pokemon.type2">
                p</pokemon-card>
        </div>
    </section>
</template>

<style lang="scss" scoped>

</style>