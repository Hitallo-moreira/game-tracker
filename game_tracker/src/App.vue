<template>
  <div>
    <GameHeader />
    <SearchBar />
    <GameFilter />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import SearchBar from './components/SearchBar/SearchBar.vue'
import GameFilter from './components/Filter/GameFilter.vue'
import GameFooter from './components/Footer/GameFooter.vue'

export default {
  components: {
    GameHeader,
    SearchBar,
    GameFilter,
    GameFooter
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/base/_variables.scss";
@import "@/assets/scss/base/reset.scss";
</style>
