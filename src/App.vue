<script>
import axios from 'axios'
import { store } from './data/store'
import PokemonList from './components/Pokemonlist.vue';
export default {
  components: { PokemonList },
  data() {
    return {
      store
    }
  },
  methods: {
    fetchPokemons(url) {
      axios.get(url).then(res => {
        store.pokemons = res.data.docs
      })
    }
  },
  created() {
    this.fetchPokemons(store.apiUri);
  }
}
</script>

<template>
  <header class="text-center">
    <img class="my-5" src="https://archives.bulbagarden.net/media/upload/4/4b/Pok%C3%A9dex_logo.png" alt="pokedex">
  </header>
  <main class="container">
    <pokemon-list></pokemon-list>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>