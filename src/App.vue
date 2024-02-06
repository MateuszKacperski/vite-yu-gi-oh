<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
import { store } from './data/store.js';
import AppMain from './components/AppMain.vue'
import AppHeader from './components/AppHeader.vue'
export default {
  name: 'Pokèvuex',
  data: () => ({
    types: ["Bug",
      "Dark",
      "Dragon",
      "Electric",
      "Fairy",
      "Fighting",
      "Fire", "Flying", "Ghost"
      , "Grass", "Ground",
      "Ice", "Normal",
      "Poison", "Psychic",
      "Rock", "Steel", "Water"]
  }),
  methods: {
    sortType(type) {
      const sortEndpoint = `${endpoint}?eq[type1]=${type}`;
      return store.pokemons = sortEndpoint;
    }
  },
  components: {
    AppMain, AppHeader
  },
  created() {
    axios.get(endpoint).then(res => {
      store.pokemons = res.data.docs;
    })
  }
}
</script>

<template>
  <AppHeader :types="types" @send-type="sortType" />
  <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.scss';
</style>
