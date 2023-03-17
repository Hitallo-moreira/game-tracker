<template>
  <div>
    <GameHeader />
    <SearchBar />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import SearchBar from './components/SearchBar/SearchBar.vue'
import GameFooter from './components/Footer/GameFooter.vue'

export default {
  components: {
    GameHeader,
    SearchBar,
    GameFooter
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/_variables.scss";
@import "@/assets/scss/reset.scss";
</style>
