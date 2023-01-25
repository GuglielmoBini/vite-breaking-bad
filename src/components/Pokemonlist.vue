<script>
import { store } from '../data/store';
import PokemonCard from './PokemonCard.vue';
export default {
    name: 'PokemonList',
    components: { PokemonCard },
    data() {
        return { store }
    },
};
</script>

<template>
    <section id="pokemon">
        <div class="row justify-content-center mb-5">
            <pokemon-card v-for="pokemon in store.pokemons" :key="pokemon._id" :name="pokemon.name"
                :image="pokemon.imageUrl" :number="pokemon.number" :type1="pokemon.type1" :type2="pokemon.type2">
                p</pokemon-card>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.row {
    background-color: aqua;
    border-radius: 25px;
    border: 3px black solid;
    padding: 15px;
}
</style>