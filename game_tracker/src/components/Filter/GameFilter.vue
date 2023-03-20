<template>
    <div class="main heading-options order-by">
        <p class="filter-title">Ordernar por:</p>
        <select name="filters" id="filters">
            <option value="" v-for="(filter_name, index) in filters" v-bind:key="index"> {{ filter_name }} </option>
        </select>
    </div>
</template>

<script>
export default {
    name: "GameFilter",
    data() {
        return {
            filters: ['% de Desconto', 'Maior preço', 'Menor preço', 'Título']
        }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/_filter.scss";
</style>