<script>
export default {
    name: 'AppHeder',
    props: {
        types: Array
    },
    emits: ['send-type']
}
</script>
<template>
    <header class="container">
        <div class="d-flex justify-content-between">
            <h1 class="text-center my-5 align-self-center">Pokèvuex</h1>
            <form>
                <select class="form-select ">
                    <option selected>All</option>
                    <option v-for="(type, i) in types" :key="i" :value="type" @submit="$emit('send-type', type)">
                        {{ type }}
                    </option>
                </select>
            </form>
        </div>
    </header>
</template>
<style lang="scss" scoped>
select {
    max-width: 150px;
    max-height: 50px;
}
</style>