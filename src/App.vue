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
  <header>
    <h1 class="text-uppercase text-center my-5">Pokèdex</h1>
  </header>
  <main class="container">
    <pokemon-list></pokemon-list>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>