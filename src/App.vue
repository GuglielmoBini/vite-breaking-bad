<script>
import AppMain from './components/AppMain.vue';
export default {
  components: { AppMain }
}
</script>

<template>
  <header>
    <h1 class="text-uppercase text-center my-5">Pokèdex</h1>
  </header>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>