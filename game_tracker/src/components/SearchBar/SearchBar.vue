<template>
    <div class="main search">
        <h1 class="title">{{ title }}</h1>
        <input type="text" id="searchbar" placeholder="Procurar">
    </div>
</template>

<script>
export default {
    name: "SearchBar",
    data() {
        return {
            title: 'Ofertas'
        }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/_searchbar.scss";
</style>