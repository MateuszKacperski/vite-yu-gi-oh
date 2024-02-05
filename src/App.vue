<script>
import AppMain from './components/AppMain.vue'
export default {
  name: 'Pokèvuex',
  components: {
    AppMain
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
