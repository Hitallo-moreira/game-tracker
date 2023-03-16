<template>
  <div>
    <GameHeader />
    <GameFooter />
  </div>
</template>

<script>
import GameHeader from './components/Header/GameHeader.vue'
import GameFooter from './components/Footer/GameFooter.vue'

export default {
  components: {
    GameHeader,
    GameFooter
  }
}

</script>

<style lang="scss">
@import "@/assets/scss/_variables.scss";
@import "@/assets/scss/reset.scss";
</style>
