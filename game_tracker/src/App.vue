<template>
  <div>
    <GameHeader />
    <div class="main heading-options">
      <SearchBar />
      <GameFilter />
    </div>
    <GameCard />
    <LoadButton />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import SearchBar from './components/SearchBar/SearchBar.vue'
import GameFilter from './components/Filter/GameFilter.vue'
import GameFooter from './components/Footer/GameFooter.vue'
import GameCard from './components/Card/GameCard.vue'
import LoadButton from './components/LoadButton/LoadButton.vue'

export default {
  components: {
    GameHeader,
    SearchBar,
    GameFilter,
    GameCard,
    LoadButton,
    GameFooter
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/base/_variables.scss";
@import "@/assets/scss/base/reset.scss";
</style>
