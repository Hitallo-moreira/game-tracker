<template>
  <div>
    <GameHeader />
    <GameFooter />
    <SearchBar />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import GameFooter from './components/Footer/GameFooter.vue'
import SearchBar from './components/SearchBar/SearchBar.vue'

export default {
  components: {
    GameHeader,
    GameFooter,
    SearchBar
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/_variables.scss";
@import "@/assets/scss/reset.scss";
</style>
