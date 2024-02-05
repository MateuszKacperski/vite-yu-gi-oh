<script>
import { store } from '../data/store.js';
import AppPokemonCard from './AppPokemonCard.vue'
export default {
    name: 'AppPokemonList',
    data: () => ({
        store
    }),
    components: {
        AppPokemonCard
    }
}
</script>
<template>
    <div class="my-5">
        <div class="row g-3 row-cols-3">
            <div class="col" v-for="pokemon in store.pokemons" :key="pokemon.id">
                <AppPokemonCard :name="pokemon.name" :number="pokemon.number" :type="pokemon.type1"
                    :image="pokemon.imageUrl" />
            </div>
        </div>

    </div>
</template>
<style lang="scss"></style>