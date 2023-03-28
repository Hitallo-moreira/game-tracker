<template>
    <div>
        <h1 class="title">{{ title }}</h1>
        <div class="search">
            <input type="text" id="searchbar" placeholder="Procurar">
        </div>
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