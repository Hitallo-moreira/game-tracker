<template>
  <div>
    <nav class="menu">
      <div class="main logo">
        <a href="#">
          <img class="logo-img" :src="logo_src" :alt="logo_alt">
        </a>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: "GameHeader",
  data() {
    return {
      logo_src: '/img/logo.svg',
      logo_alt: 'Game Tracker logo'
    }
  }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/_header.scss";
</style>