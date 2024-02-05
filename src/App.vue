<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
import { store } from './data/store.js';
import AppMain from './components/AppMain.vue'
export default {
  name: 'Pokèvuex',
  components: {
    AppMain
  },
  created() {
    axios.get(endpoint).then(res => {
      store.pokemons = res.data.docs;
    })
  }
}
</script>

<template>
  <header>
    <h1 class="text-center my-5">Pokèvuex</h1>
  </header>
  <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss';
</style>
