<template>
  <div>
    <nav class="menu">
      <div class="main logo">
        <img class="logo-img" :src="logo_src">
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "GameHeader",
  data() {
    return {
      logo_src: '/img/logo.svg'
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/_header.scss";
</style>