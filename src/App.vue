<script>
import axios from 'axios'
import { store } from './data/store'
import SelectFilter from './components/SelectFilter.vue';
import PokemonList from './components/Pokemonlist.vue';
export default {
  components: { SelectFilter, PokemonList },
  data() {
    return {
      store,
      apiUri:
        "https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons",
    }
  },
  computed: {
    startUri() {
      const startUrl = `${this.apiUri}?per=50&page=1`
      return startUrl;
    },
  },
  methods: {
    fetchPokemons(url) {
      axios.get(url).then(res => {
        store.pokemons = res.data.docs
      })
    },

    fetchType(url) {
      axios.get(url + '/types1').then(res => {
        store.pokemonTypes = res.data
      })
    },
    filterByType(type) {
      const byTypeUrl = !type ? this.startUri : `${this.startUri}&eq[type1]=${type}`
      this.fetchPokemons(byTypeUrl)
    }

  },
  created() {
    this.fetchType(this.apiUri)
    this.fetchPokemons(this.startUri);
  }
}
</script>

<template>
  <header class="text-center">
    <img class="my-5" src="https://archives.bulbagarden.net/media/upload/4/4b/Pok%C3%A9dex_logo.png" alt="pokedex">
    <h4 class="mb-3">Select a Type</h4>
    <select-filter @change-choice="filterByType"></select-filter>
  </header>
  <main class="container">
    <pokemon-list></pokemon-list>
  </main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>