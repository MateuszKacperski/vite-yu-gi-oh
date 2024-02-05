<script>
export default {
    name: 'AppPokemonCard',
    props: {
        number: Number,
        name: String,
        type: String,
        image: String
    }
}
</script>
<template>
    <div class="pokemon-card text-center p-2">
        <img :src="image" :alt="name" class="img-fluid rounded-circle mb-5">
        <h4>{{ number }}</h4>
        <div><strong>{{ name }}</strong></div>
        <div>{{ type }}</div>
    </div>
</template>
<style lang="scss">
img {
    max-height: 150px;
}
</style>