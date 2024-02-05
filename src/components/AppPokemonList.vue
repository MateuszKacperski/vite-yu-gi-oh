<script>
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons'
import AppPokemonCard from './AppPokemonCard.vue'
export default {
    name: 'AppPokemonList',
    data: () => ({
        pokemons: []
    }),
    components: {
        AppPokemonCard
    },
    created() {
        axios.get(endpoint).then(res => {
            this.pokemons = res.data.docs;
        })
    }
}
</script>
<template>
    <div class="my-5">
        <div class="row g-3 row-cols-3">
            <div class="col" v-for="pokemon in pokemons" :key="pokemon.id">
                <AppPokemonCard :name="pokemon.name" :number="pokemon.number" :type="pokemon.type1"
                    :image="pokemon.imageUrl" />
            </div>
        </div>

    </div>
</template>
<style lang="scss"></style>