<template>
  <div>
    <GameHeader />
    <GameCard />
    <LoadButton />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import GameFooter from './components/Footer/GameFooter.vue'
import GameCard from './components/Card/GameCard.vue'
import LoadButton from './components/LoadButton/LoadButton.vue'

export default {
  components: {
    GameHeader,
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
