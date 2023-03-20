<template>
  <div>
    <GameHeader />
    <SearchBar />
    <GameFilter />
    <GameCard />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import SearchBar from './components/SearchBar/SearchBar.vue'
import GameFilter from './components/Filter/GameFilter.vue'
import GameFooter from './components/Footer/GameFooter.vue'
import GameCard from './components/Card/GameCard.vue'

export default {
  components: {
    GameHeader,
    SearchBar,
    GameFilter,
    GameCard,
    GameFooter
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/base/_variables.scss";
@import "@/assets/scss/base/reset.scss";
</style>
